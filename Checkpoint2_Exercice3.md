## Q 3.1
Le matériel A est un switch il agit sur la couche 2 du modele OSI, en général, il permet d'avoir des  "autoroutes" entre nos réseaux, sur notre réseaux il permet de relier tout nos PC au routeur B 

## Q 3.2
Le matériel B est un routeur il agit quand a lui sur la couche 3 du modèle OSI, en générale se sont les "panneaux de direction" de nos "autoroutes" il redirige les paquets qu'on lui "envoie" au endroit configuré. Dans notre réseaux il sert de passerelle pour les PC appartenant au réseaux 10.10.0.0/16 et donc leurs permette de communiqué avec d'autre réseaux

## Q 3.3
f0/0 et g1/0 corresponde au nom de ses interfaces, vulgairement parlant ses cartes réseaux, on constate donc que notre routeur a 2 interfaces, la f0/0 qui a pour adresse **IPv4 : 10.10.255.254/16** et adresse **MAC : CA:01:DA:D2:00:08** et la g1/0 a pour adresse **IPv4 : 10.12.2.254/24** et adresse **MAC : CA:01:DA:D2:00:1C**
## Q 3.4
/16 représente pour PC2 son masque de Sous réseau, cela signifie que les 16 premiers bits de sont masque de sous réseaux sont a 1 donc : 11111111.11111111.0.0 ou en notation décimal 255.255.0.0
## Q 3.5
10.10.255.254 représente pour PC2 son adresse de passerelle, si elle doit communiqué avec un autre sous réseaux, c'est a cette passerelle qu'elle va envoyé ses paquets
## Q 3.6
| |Adresse Réseaux | Premier adresse disponible | Dernier adresse Disponible | Adresse de Broadcast|
| :---: | :---: | :---: | :---: | :---: |
|PC 1|10.10.0.0|10.10.0.1|10.10.255.254|10.10.255.255|
|PC 2|10.11.0.0|10.11.0.1|10.11.255.254|10.11.255.255|
|PC 3|10.10.0.0 |10.10.0.1|10.10.127.254|10.10.127.255|
Méthodologie pour PC3
 1. Adresse réseaux 
	IP de notre machine : 00001010.00001011.01010000.00000010
	CIDR : 11111111.11111110.00000000.000000000
	On fait un "ET Logique" entre notre IP et son CIDR ce qui nous donne :
	00001010.00001010.00000000.00000000 ou 10.10.0.0 en décimal
2. Adresse de Broadcast
	IP de notre machine : 00001010.00001011.01010000.00000010
	CIDR inversé : 00000000.00000000.01111111.11111111
	On fait un "OU Logique" entre notre IP et son CIDR ce qui nous donne :
	00001010.00001011.01111111.11111111 ou 10.10.127.255

## Q 3.7
Un "**X**" signifie aucune communication et un "**V**" signifie que les machines communiquent sans l'intervention d'un routeur avec des routes configurer 

| |PC 1 | PC 2 | PC 3 | PC 4 | PC 5 |
| :---: | :---: | :---: | :---: | :---: | :---: |
|PC 1|X|X|V|V|V|
|PC 2|X|X|X|X|X|
|PC 3|V|X|X|V|V|
|PC 4|V|X|V|X|V|
|PC 5|V|X|V|V|X|
## Q 3.8

PC1, PC3, et PC4 peuvent atteindre le réseaux 172.16.5.0/24 
PC2, et PC5 ne peuvent pas l'atteindre car il ne sont pas sur le même sous réseaux que le routeur 10.10.255.254/16
## Q 3.9
Il n'y aura aucune incidence car le port de connexion ne défini pas le sous réseaux sur lesquels nos PC sont actuellement.
## Q 3.10
Non traité
## Q 3.11
L'adresse MAC qui initialise la communication est : 00:50:79:66:68:00. Grace au informations Ordinateur j'en déduis qu'il s'agit du PC1
## Q 3.12
La communication a effectivement réussi car dans la colonne Info on s'aperçois que les paquet alterne entre "**request**" et "**reply**".
## Q 3.13
Request correspond au PC1 dans cette capture 
Reply correspond au PC4 dans cette capture

|Matériel|Adresse MAC|Adresse IP|
|---|---|---|
|PC1|00:50:79:66:68:00|10.10.4.1/16|
|PC4|00:50:79:66:68:03|10.10.4.2/16|
## Q 3.14
Le protocole encapsulé dans le paquet 2 est le protocole ARP
## Q 3.15
Ils n'ont pas interagie dans la communication
## Q 3.16

C'est le PC3 qui initialise la communication son adresse ip est la suivante 10.10.80.3/16
## Q 3.17
ICMP
## Q 3.18
Non la communication a raté, on peut voir dans la colonne Info "Destination unreachable (Host unreachable)" car comme précisé a la question 3.8 le routeur n'etant pas sur le meme reseaux que PC3 il ne peut pas communiquer avec 10.11.80.2 (PC2)
## Q 3.19
N'étant pas sur le même réseaux et n'ayant aucune interface de passerelle le paquet n'est jamais arrivé sur PC2.
## Q 3.20
Ils n'ont pas interagie dans la communication
## Q 3.21
Le matériel sources est le : 

|  Matériel | Adresse MAC  |  Adresse IP |
|---|---|---|
|PC4|00:50:79:66:68:03|10.10.4.2/16|

Le matériel de destination est inconnue, nous n'avons que son adresse IP qui est 172.16.5.253, donc j'en déduis qu'il sagit d'une interface sur le réseaux 172.16.5.0/24 qui se situe apres notre routeur R2
## Q 3.22
L'adresses Mac source est le : 

|Matériel|Interface|Adresse MAC|Adresse IP|
|---|---|---|---|
|B|g1/0|CA:01:DA:D2:00:1C|10.12.2.254/24|

l'Adresse Mac Destinataire est le :

|Matériel|Interface|Adresse MAC|Adresse IP|
|---|---|---|---|
|R2|g2/0|CA:03:9E:EF:00:38|10.12.2.253/24|

le paquet émis depuis PC 4 a bien été reçu par le routeur B et l'envoie correctement vers le routeur R2

## Q 3.23
J'en déduis que nous observons le transferts de paquet entre le routeur B et R2