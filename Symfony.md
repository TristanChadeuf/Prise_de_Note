# Voila tes notes sur Symfony



## Exemple d'un controller

```php

<?php

namespace App\Controller;

use App\Entity\CoinCoin;
use App\Entity\Comment;
use App\Entity\Duck;
use App\Form\CoinCoinType;
use App\Form\CommentType;
use App\Form\DuckType;
use App\Form\SearchType;
use App\model\SearchData;
use App\Repository\CoinCoinRepository;
use App\Repository\CommentRepository;
use App\Service\UploaderQuackPicture;
use Doctrine\ORM\EntityManagerInterface;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\DependencyInjection\Attribute\Autowire;
use Symfony\Component\HttpFoundation\File\Exception\FileException;

use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\PasswordHasher\Hasher\UserPasswordHasherInterface;
use Symfony\Component\Routing\Attribute\Route;
use Symfony\Component\Security\Http\Authentication\AuthenticationUtils;
use Symfony\Component\String\Slugger\SluggerInterface;

#[Route('/coincoin')]
final class CoinCoinController extends AbstractController
{
    #[Route('/new', name: 'app_coin_coin_new', methods: ['GET', 'POST'])]
    public function new(Request $request, SluggerInterface $slugger, UploaderQuackPicture $uploaderQuackPicture,EntityManagerInterface $em): Response
    {
        $user = $this->getUser();

        $product = new CoinCoin();
        $product->setAuthor($user);

        $form = $this->createForm(CoinCoinType::class, $product);
        $form->handleRequest($request);

        if ($form->isSubmitted() && $form->isValid()) {


            $picture = $form->get('picture')->getData();

            if ($picture) {
                $uploadedPicturePath = $uploaderQuackPicture->uploadQuackImage($picture);
                $product->setPicture($uploadedPicturePath);
            }



            $em->persist($product);
            $em->flush();


            return $this->redirectToRoute('app_coin_coin_index');
        }

        return $this->render('coin_coin/new.html.twig', [
            'form' => $form,
        ]);
    }

    #[Route('/{id}', name: 'app_coin_coin_show', methods: ['GET', 'POST'])]
    public function show(CoinCoin $coinCoin,  Request $request, EntityManagerInterface $entityManager): Response
    {
        $comment = new Comment();
        $comment->setCoinCoin($coinCoin);
        $comment->setDuck($this->getUser());
        $form = $this->createForm(CommentType::class, $comment);
        $form->handleRequest($request);
        if ($form->isSubmitted() && $form->isValid()) {
            $entityManager->persist($comment);
            $entityManager->flush();
            return $this->redirectToRoute('app_coin_coin_show', ['id' => $coinCoin->getId()]);
        }
        return $this->render('coin_coin/show.html.twig', [
            'coin_coin' => $coinCoin,
            'commentForm' => $form->createView(),
        ]);
    }

    #[Route('/{id}/edit', name: 'app_coin_coin_edit', methods: ['GET', 'POST'])]
    public function edit(Request $request, CoinCoin $coinCoin, EntityManagerInterface $entityManager): Response
    {
        $form = $this->createForm(CoinCoinType::class, $coinCoin);
        $form->handleRequest($request);

        if ($form->isSubmitted() && $form->isValid()) {
            $entityManager->flush();

            return $this->redirectToRoute('app_coin_coin_index', [], Response::HTTP_SEE_OTHER);
        }

        return $this->render('coin_coin/edit.html.twig', [
            'coin_coin' => $coinCoin,
            'form' => $form,
        ]);
    }

    #[Route('/{id}/delete', name: 'app_coin_coin_delete', methods: ['POST'])]
    public function delete(Request $request, CoinCoin $coinCoin, EntityManagerInterface $entityManager): Response
    {
        if ($this->isCsrfTokenValid('delete'.$coinCoin->getId(), $request->getPayload()->getString('_token'))) {
            $entityManager->remove($coinCoin);
            $entityManager->flush();
        }

        return $this->redirectToRoute('app_coin_coin_index', [], Response::HTTP_SEE_OTHER);
    }


    #[Route(name: 'app_coin_coin_index', methods: ['GET', 'POST'])]
    public function index(CoinCoinRepository $coinCoinRepository, Request $request, EntityManagerInterface $entityManager, CommentRepository $commentRepository): Response
    {
        $coincoins = $coinCoinRepository->findAll();

        $searchData= new SearchData();

        $form = $this->createForm(SearchType::class, $searchData, [
            'csrf_token_id' => "formSearch",
        ]);
        $form->handleRequest($request);
        if ($form->isSubmitted() && $form->isValid()) {
            $coincoins = $coinCoinRepository->findBySearch($searchData);
        }

        return $this->render('coin_coin/index.html.twig', [
            'form'=>$form,
            'coincoins' => $coincoins,

        ]);
    }
}
```
## Exemple Entity

```php
<?php

namespace App\Entity;

use AllowDynamicProperties;
use App\Repository\CoinCoinRepository;
use App\Repository\CommentRepository;
use Doctrine\Common\Collections\ArrayCollection;
use Doctrine\Common\Collections\Collection;
use Doctrine\DBAL\Types\Types;
use Doctrine\ORM\Mapping as ORM;

#[AllowDynamicProperties] #[ORM\Entity(repositoryClass: CoinCoinRepository::class)]

class CoinCoin
{
    public function __construct()
    {
        $this->created_at = new \DateTime();
        $this->comments = new ArrayCollection();

    }
    #[ORM\Id]
    #[ORM\GeneratedValue]
    #[ORM\Column]
    private ?int $id = null;

    #[ORM\Column(length: 150)]
    private ?string $Post = null;

    #[ORM\Column(length: 255)]
    private ?string $Picture = null;

    #[ORM\Column(type: Types::DATETIME_MUTABLE)]
    private ?\DateTimeInterface $created_at = null;

    #[ORM\Column(length: 50)]
    private ?string $Tags = null;


    #[ORM\ManyToOne(inversedBy: 'coinCoins')]
    #[ORM\JoinColumn(nullable: false)]
    private ?Duck $author = null;

    /**
     * @var Collection<int, Comment>
     */
    #[ORM\OneToMany(targetEntity: Comment::class, mappedBy: 'coincoin')]
    private Collection $comments;

    //GETTER SETTER*****************************************************************************************************
    public function getId(): ?int
    {
        return $this->id;
    }

    public function getPost(): ?string
    {
        return $this->Post;
    }

    public function setPost(string $Post): static
    {
        $this->Post = $Post;

        return $this;
    }

    public function getDuckName(): ?string
    {
        return $this->DuckName;
    }

    public function setDuckName(string $DuckName): static
    {
        $this->DuckName = $DuckName;

        return $this;
    }

    public function getPicture(): ?string
    {
        return $this->Picture;
    }

    public function setPicture(string $Picture): static
    {
        $this->Picture = $Picture;

        return $this;
    }

    public function getCreatedAt(): ?\DateTimeInterface
    {
        return $this->created_at;
    }

    public function setCreatedAt(\DateTimeImmutable $created_at): static
    {
        $this->created_at = $created_at;

        return $this;
    }


    public function getTags(): ?string
    {
        return $this->Tags;
    }

    public function setTags(string $Tags): static
    {
        $this->Tags = $Tags;

        return $this;
    }

    public function getAuthor(): ?Duck
    {
        return $this->author;
    }

    public function setAuthor(?Duck $author): static
    {
        $this->author = $author;

        return $this;
    }

    public function setDuck(?\Symfony\Component\Security\Core\User\UserInterface $getUser)
    {

    }

    /**
     * @return Collection<int, Comment>
     */
    public function getComments(): Collection
    {
        return $this->comments;
    }

    public function addComment(Comment $comment): static
    {
        if (!$this->comments->contains($comment)) {
            $this->comments->add($comment);
            $comment->setCoincoin($this);
        }

        return $this;
    }

    public function removeComment(Comment $comment): static
    {
        if ($this->comments->removeElement($comment)) {
            // set the owning side to null (unless already changed)
            if ($comment->getCoincoin() === $this) {
                $comment->setCoincoin(null);
            }
        }

        return $this;
    }
}
```

## Exemple Form 

```php

namespace App\Form;

use App\Entity\CoinCoin;
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\Extension\Core\Type\FileType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolver;
use Symfony\Component\Validator\Constraints\File;
use Symfony\Component\Validator\Constraints\Image;

class CoinCoinType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options): void
    {
        $builder
            ->add('Post')
            ->add('picture', FileType::class,[
            'label' => false,
            'required' => false,
            'mapped' => false,
            'constraints' => [
                new Image([
                    'mimeTypes' => [
                        'image/jpeg',
                        'image/png',
                        'image/gif',
                    ],
                    'mimeTypesMessage' => "Veuillez télécharger une image valide",
                    "maxSize" => '4M',
                    'maxSizeMessage' => "Votre image fait {{size}} {{suffix}}, La limite est de {{ limit }} {{suffix}}"
                ]),
            ]
        ])
            ->add('Tags');
    }

    public function configureOptions(OptionsResolver $resolver): void
    {
        $resolver->setDefaults([
            'data_class' => CoinCoin::class,
        ]);
    }
}
```

## Exemple Repository

```php

<?php

namespace App\Repository;

use App\Entity\CoinCoin;
use App\model\SearchData;
use Doctrine\Bundle\DoctrineBundle\Repository\ServiceEntityRepository;
use Doctrine\ORM\Tools\Pagination\Paginator;
use Doctrine\Persistence\ManagerRegistry;

/**
 * @extends ServiceEntityRepository<CoinCoin>
 */
class CoinCoinRepository extends ServiceEntityRepository
{
    public function __construct(ManagerRegistry $registry)
    {
        parent::__construct($registry, CoinCoin::class);
    }
    public function findBySearch(SearchData $searchData):array
    {
        $posts = $this->createQueryBuilder('p')
            ->join('p.author', 'd')
            ->addSelect('d');

        if (!empty($searchData->query)){
            $posts = $posts

                ->where('d.duckName LIKE :query')
                ->setParameter('query', "%" .  $searchData->query ."%");
        }
        $posts = $posts
            ->getQuery()
            ->getResult();

        return $posts;

    }
    //    /**
    //     * @return CoinCoin[] Returns an array of CoinCoin objects
    //     */
    //    public function findByExampleField($value): array
    //    {
    //        return $this->createQueryBuilder('c')
    //            ->andWhere('c.exampleField = :val')
    //            ->setParameter('val', $value)
    //            ->orderBy('c.id', 'ASC')
    //            ->setMaxResults(10)
    //            ->getQuery()
    //            ->getResult()
    //        ;
    //    }

    //    public function findOneBySomeField($value): ?CoinCoin
    //    {
    //        return $this->createQueryBuilder('c')
    //            ->andWhere('c.exampleField = :val')
    //            ->setParameter('val', $value)
    //            ->getQuery()
    //            ->getOneOrNullResult()
    //        ;
    //    }
}
```
## Exemple Twig

```php

{% extends 'base.html.twig' %}

{% block title %}CoinCoin index{% endblock %}

{% block body %}
    {{ include('coin_coin/search_data.html.twig') }}
    <h1>CoinCoin</h1>

    <table>
        <thead>
            <tr>
                <th>Post</th>
                <th>DuckName</th>
                <th>Picture</th>
                <th>Created At</th>
                <th>Tags</th>
                <th>actions</th>
            </tr>
        </thead>
        <tbody>

        {% for coin_coin in coincoins %}
            <tr>
                <td>{{ coin_coin.Post }}</td>
                <td>{{ coin_coin.author.duckName }}</td>
                <td><img src="{{ coin_coin.Picture }}" style="width: 100%"></td>
                <td>{{ coin_coin.createdAt ? coin_coin.createdAt|date('Y-m-d H:i:s') : '' }}</td>
                <td>{{ coin_coin.Tags }}</td>

                <td>
                    <ul>
                        {% for comment in coin_coin.comments %}
                        <li>
                            {{ comment.text}}
                        </li>
                        {% endfor %}
                    </ul>
                </td>

                <td>
                    {% if is_granted("ROLE_USER","ROLE_ADMIN") %}
                    <button class="btn btn-warning"><a href="{{ path('app_coin_coin_show', {'id': coin_coin.id}) }}">show</a></button>
                    {% endif %}

                        {% if is_granted("ROLE_ADMIN") %}
                        <button class="btn btn-danger"><a href="{{ path('app_coin_coin_edit', {'id': coin_coin.id}) }}">edit</a></button>
                    {% endif %}

                </td>

            </tr>
        {% else %}
            <tr>
                <td colspan="7">no records found</td>
            </tr>
        {% endfor %}
        </tbody>
    </table>
        {% if is_granted("ROLE_USER", "ROLE_ADMIN ") %}
            <button class="btn btn-primary"><a href="{{ path('app_coin_coin_new') }}">Create new</a></button>
        {% endif %}
{% endblock %}
```
