## Q1.1
Le client et le serveur ne se ping pas car il ne se trouve pas sur le même réseaux 
l'adresse IPv4 du serveur est le 172.16.10.10/24, il a donc pour adresser réseaux 172.16.10.0
l'adresse IPV4 du client est le 172.16.100.50/24, il a donc pour adresse réseaux 172.16.100.0
Pour faire en sorte que les deux machine se ping, je vais laissé mon client en static et modifié son adresse IPv4 pour qu'elle fasse partie de l'adresse réseaux du serveur :
- Allez dans les paramètre de votre carte réseaux du client
- Entrer dans les propriétés de "**Internet Protocol Version 4 (TCP/IPv4) Properties**" 
- Entrer une adresse IPv4 valide 
![[Pasted image 20231117094332.png]]
- J'en profite pour renseigner le DNS par défaut de ma machine client 
- J'essayer de ping mon serveur depuis ma machine pour vérifier que ma manipulation à fonctionné 
![[Pasted image 20231117094632.png]]
- Je termine ma vérification par un ping depuis mon serveur vers mon client 
 ![[Pasted image 20231117094756.png]]

## Q 1.2
A ne pas traiter

## Q 1.3
J'ai donc modifié la configuration réseaux de mon client en DHCP, j'ai obtenu l'adresse IP suivante :
![[Pasted image 20231117095115.png]]

Par un hasard qui n'en n'ai pas un, j'ai obtenu la même adresse IP que celle que j'avais fixé, cela est du a la configuration de notre serveur DHCP, dans le DHCP Manager, on peut constater que notre plage réseaux exclu les adresses 172.16.10.1 à 172.16.10.19 et 172.16.10.241 à 172.16.10.254 de notre distribution et donc la première adresse disponible de notre role DHCP est bien la 172.16.10.20

## Q 1.4
Cela est possible, il suffit juste de crée une réservation pour le client sur le rôle DHCP, pour cela il suffit juste de faire un clique droit sur l'onglet **Réservation** et de configurer l'IP 172.16.10.15 pour l'adresse MAC de la carte réseaux du client comme dans la capture d'écran ci dessous :
![[Pasted image 20231117101254.png]]

Comme on peut le voir sur l'ipconfig suivant l'IPv4 de notre client est bien en 172.16.10.15
![[Pasted image 20231117101732.png]]