# protocole-syslog
Découverte du protocole SysLog

### Qu'est-ce que le protocole Syslog?
```
Le protocole Syslog est utilisé depuis plusieurs dizaines d’années comme moyen de transport des messages entre des
périphériques réseau et un serveur de journalisation, généralement appelé serveur Syslog. En raison de sa longévité
et de sa popularité, le protocole Syslog est pris en charge sur la plupart des systèmes d’exploitation, dont macOS,
Linux et Unix. Syslog est également pris en charge sur Microsoft Windows via des outils tiers.
```

![image](https://user-images.githubusercontent.com/83721477/168556535-37392dcc-eaed-462c-8ce6-d03338d2d3a8.png)


L’usage de Syslog:
* Sécurité/autorisations/audit<br>Syslog peut être configuré pour transférer tous les événements d’authentification à un serveur syslog, sans qu’il soit nécessaire d’installer et de paramétrer un agent de supervision en tant que tel.<br>Syslog permet par ailleurs de s’assurer que les événements critiques sont enregistrés et stockés hors du serveur d’origine. Le premier réflexe d’un attaquant qui vient d’infiltrer un système est de couvrir les traces qu’il a laissées dans le journal. Heureusement, les événements transmis via syslog lui seront inaccessibles.

* Surveillance des applications

* Supervision des applications

## Principe de fonctionnement
Syslog se sert du protocole `UDP` via le `port 514`, mais on peut le configurer pour utiliser n’importe quel port.<br>En outre, certains appareils s’appuient sur TCP 1468 pour envoyer des données syslog de manière à accuser réception des messages.

Un message Syslog contient les éléments suivants :
* En-tête
* Données structurées
* Message

Les messages de journal doivent être encodés en UTF-8 ; hormis cette exigence, les messages peuvent être configurés selon les besoins de chacun. La flexibilité du contenu du message est l’une des raisons qui font que Syslog est si populaire et efficace.<br>

Les niveaux de sécurité des messages Syslog vont de 0, qui signale une urgence, à 5, qui est un avertissement. Il existe des options facultatives pour les messages d’information (niveau 6) et de débogage (niveau 7).
