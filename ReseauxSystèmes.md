# Salut voila tes notes sur Reseaux et Systèmes

- Pour vous, qu’est ce qu’un réseau ?

Le réseau informatique désigne les appareils informatiques interconnectés qui peuvent échanger des données et partager des ressources entre eux. Ces appareils en réseau utilisent un système de règles, appelées protocoles de communication, pour transmettre des informations sur des technologies physiques ou sans fil.

- Quel est le lien entre la notion de réseau et Internet ?

Un réseau désigne un ensemble d'appareils connectés dans une zone limitée, comme une maison, un bureau ou un campus. En revanche, Internet est un réseau mondial de réseaux, qui s'étend sur toute la planète et connecte des milliards d'appareils situés dans divers endroits .

- Quelle est la différence entre Internet et le Web ? Ou a-t-il été inventé ?

Internet est une plateforme qui permet de faire parvenir des informations d'un ordinateur à un autre. Le web, lui, est un moyen de visiter des pages de sites à partir de navigateurs via des ordinateurs, des tablettes ou des smartphones.
Le web a été créér au CERN à Geneve.



# Quels sont les différents types de réseaux informatiques ? Pour chaque type de réseau, donner un exemple concret. 


## Le pan (Personal Area Network)

Le PAN permet d’échanger des données entre des appareils proches (généralement dans la même pièce). Pour ce faire, il existe 2 techniques de transmission physique, l’USB et le FireWire. Il est également possible de relier deux appareils via le WPAN (réseau personnel sans fil) avec des technologiques comme l’USB sans fil, le Bluetooth ou le Z-Wave.

Il est également possible de relier un réseau PAN vers d’autres réseaux plus grands. 

## Le lan (Local Area Network)
Si vous avez besoin de relier plusieurs ordinateurs sur un réseau, vous créez un LAN ou réseau local. Pour ce faire, nous utilisons le plus souvent le protocole Ethernet.

Pour connecter plus de 2 ordinateurs ensemble, il est nécessaire d’ajouter d’autres éléments, comme un hub ou un commutateur réseau. Ces éléments agissent comme des noeuds de distribution ou des éléments de couplage. 

Le LAN permet de transmettre une grande quantité de données rapidement. Celui-ci vous permet de partager des serveurs de fichiers, imprimantes ou encore des applications. 

Il est également possible de se connecter via le WLAN (Wireless Local Area Network) ou réseau local sans fil (Wifi). 

Bien que les deux solutions soient possibles, l’Ethernet offre plus de sécurité et un débit de données plus important.

## Le man (Metropolitan Area Network)
Le MAN permet de relier plusieurs LAN proches. Celui-ci permet d’échanger très rapidement des données entre différentes branches d’une société par exemple. En utilisant la fibre optique et des routeurs assez puissants, l’échange de données est plus rapide que via l’internet. 

## Le wan (Wide Area Network)
Le WAN permet de relier différentes machines très éloignées (à l’échelle d’un continent). Pour ce faire, le WAN se base sur les technologies des adresses IP, de SDH ou encore des ATM.

Les WAN sont souvent gérés par nos fournisseurs de services Internet. 

## Le gan (Global Area Network) 
Basiquement, internet est un GAN, un réseau mondial permettant d’échanger des informations entre différents appareils. Mais internet n’est pas le seul GAN. De nombreuses entreprises utilisent un GAN pour relier différents WAN ensemble. Les GAN utilisent des câbles sous marins et des transmissions par satellite.

## Les différents réseaux informatiques le VPN
Un VPN est un réseau de communication virtuel utilisant un réseau physique, mais éloigné de l’utilisateur. Cela permet de garantir une confidentialité des données échangées sur un serveur public comme internet. Sachant que seules les données ne sont pas visibles que par les autres utilisateurs du réseau, l’on parle de Tunneling entre les deux utilisateurs.

Ces sigles sont généralement utilisés par des informaticiens réseau, cependant, il est important de comprendre comment fonctionne l’échange de données au sein de son entreprise.

# Quels sont les principaux équipements physiques d’un réseau LAN ?

Les LAN connectés à Internet les plus simples n'ont besoin que d'un routeur et d'un moyen de connecter les appareils informatiques à celui-ci, par exemple des câbles Ethernet ou un hotspot WiFi.


![MVC](./image/Reseaux_locaux.webp)



# Qu’est ce que la commande ping ? A quoi sert-elle ?

La commande ping envoie une demande ECHO_REQUEST ICMP (protocole de message de gestion interréseau) pour recevoir une réponse ECHO RESPONSE ICMP d'un hôte ou d'une passerelle. La commande ping sert à : Déterminer l'état du réseau et de divers hôtes étrangers.

![MVC](./image/table-de-ping-pong-1.jpg)

