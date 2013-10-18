###############################################################################
Proxy Suite 
Voici les sources de Suse ftp proxy avec les modifications non incluses dans 
la version Suse officielle (Plus d'infos http://traceroot.fr/).

Un proxy FTP est un serveur o� s'ex�cute un relais transf�rant les transactions FTP
depuis votre client vers un site FTP

Pour compiler Proxy-Suite avec ldap il vous faut les paquets openldap-devel et libwrap-dev
( libldap2-dev et libwrap0-dev suivant les distributions )

./configure --prefix=/usr --exec-prefix=/usr --sysconfdir=/etc --with-libldap=/usr/lib/libldap.so.2

Sous Debian etch il suffit d'installer le paque ftp-proxy et de remplacer le binaire, je suppose que �a fonctionne
pour d'autres distributions.

Voici la liste des modifications que j'ai apport�s au produit Suse ftp-proxy-suite.

- Correction: Faille de s�cu de l'appli pour l'identification Ldap (mot de passe blanc).

- Ajout: V�rification de l'appartenance � un groupe pour l'utilisateur

- Ajout: Syst�me de filtrage.

- Format des logs

Le Proxy FTP modifi� inclut maintenant des fonctionnalit�s de filtrage d'acc�s avanc�es, 
bas�es sur des ACL, listes de commandes disponibles sur des groupes (utilsateurs et destinations),

le Proxy FTP intercepte tous les flux � destination des serveurs FTP et bloque imm�diatement 
les sites interdits, restreint les commandes ftp pour d'autres, ou bien autorise toutes les connections.
