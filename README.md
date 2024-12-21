# Dans ce tutoriel, nous allons explorer et pratiquer des commandes Unix avancées pour surveiller une machine Unix.

### N'hésitez pas à nous contacter en cas de doute: naimiatef@gmail.com
# La commande **top** 
La commande **top** sous Unix est un outil interactif qui permet de surveiller en temps réel les processus en cours d'exécution sur une machine. Elle affiche des informations clés telles que :

- L'utilisation du CPU.
- La mémoire (RAM et swap).
- Les tâches actives, dormantes ou en attente.
- Les utilisateurs et la priorité des processus.
- C'est un outil essentiel pour analyser les performances et identifier les processus qui consomment le plus de ressources.
![image](https://github.com/user-attachments/assets/72c4d053-6fad-46ac-984f-2bbef7ab3267)
Cette image montre l'affichage de la commande top dans un terminal Linux, qui sert à surveiller en temps réel les performances et les processus d'une machine Unix. <br>
### En-tête générale :<br>
- **top** - 14:47:38 : Heure actuelle.<br>
- **up 9 min** : Durée de fonctionnement du système depuis le dernier démarrage (ici, 9 minutes).<br>
- **users** : Nombre d'utilisateurs connectés à la machine.<br>
- **load average**: 0.05, 0.57, 0.47 : Moyenne de la charge système sur 1, 5 et 15 minutes. Ces valeurs indiquent le nombre moyen de processus en attente d'exécution.<br>
### Informations sur les tâches (Tasks) : <br>
- **209 total** : Nombre total de tâches ou processus.
- **1 running **: Nombre de processus en cours d'exécution.
- **208 sleeping** : Nombre de processus en veille.
- **0 stopped** : Aucun processus arrêté manuellement.
- **0 zombie** : Aucun processus zombie (processus terminé mais toujours en mémoire).
### Informations sur l'utilisation du CPU :
- **%Cpu(s):** Indique la répartition de l'utilisation du CPU :
- **6.2 us :** Temps passé par les processus utilisateur (user).
- **6.2 sy :** Temps passé par les processus système (kernel).
- **87.5 id :** Temps d'inactivité (idle).
Les autres valeurs concernent des tâches spécifiques comme l'attente d'entrée/sortie (wa), ou les interruptions matérielles (hi) et logicielles (si).
### Informations sur la mémoire :
- **MiB Mem :** Utilisation de la mémoire vive (RAM).
- **3654.1 total :** Capacité totale de la RAM.
- **150.3 free :** Mémoire disponible.
- **1439.8 used :** Mémoire utilisée par les processus.
- **2063.9 buff/cache :** Mémoire utilisée pour les buffers et le cache.
- **MiB Swap :** Utilisation de la mémoire swap (mémoire virtuelle sur disque).
- **4056.0 total :** Taille totale du swap.
- **4008.5 free :** Swap disponible.
- **47.5 used :** Swap actuellement utilisé.
### Tableau des processus :
Chaque ligne correspond à un processus en cours d'exécution ou en veille. Les colonnes affichent les informations suivantes :

- **PID :** Identifiant unique du processus.
- **USER :** Nom de l'utilisateur exécutant le processus.
- **PR et NI :** Priorité et valeur nice du processus (impacte la priorité d'exécution).
- **VIRT :** Mémoire virtuelle totale utilisée par le processus.
- **RES :** Mémoire physique (RAM) utilisée.
- **SHR :** Mémoire partagée par d'autres processus.
- **S :** État du processus :<br>
  - **R :** En cours d'exécution (Running).<br>
  - **S :** En sommeil (Sleeping).<br>
  - **I :** En veille inactif (Idle).<br>
- **%CPU :** Pourcentage d'utilisation du CPU par le processus.
- **%MEM :** Pourcentage d'utilisation de la RAM.
- **TIME+ :** Temps total CPU consommé par le processus.
- **COMMAND :** Nom ou commande associée au processus.
# La commande **top -o +%CPU** 
La commande top -o +%CPU est utilisée pour trier les processus affichés dans top par ordre décroissant d'utilisation du CPU. <br>
Détail des options : <br>
- **-o :** Cette option permet de spécifier une colonne selon laquelle trier les processus.
- **+%CPU :** Indique que les processus doivent être triés par la colonne %CPU (utilisation du CPU), dans un ordre décroissant (du processus consommant le plus de CPU vers le moins). <br>
![image](https://github.com/user-attachments/assets/ade2d66d-4c0b-437c-b36e-f262cd6d4b13) <br>
- Tri par la colonne %CPU :
- Les processus sont affichés en fonction de leur consommation CPU, du plus élevé au plus faible.
- Ici, le processus gnome-shell (PID 2391) consomme 6.7% du CPU, ce qui en fait le plus gourmand à l'instant.
- **Colonne %CPU (surlignée) :**
Montre le pourcentage du temps CPU utilisé par chaque processus par rapport à la capacité totale.
Autres détails pertinents :

- **Le processus systemd (PID 1),** qui gère les services système, consomme très peu de CPU (0.0%).
La plupart des processus (comme kthreadd, rcu_gp, etc.) sont inactifs, avec une utilisation CPU de 0.0%.
# La commande **top -o +%MEM** 
- La commande top -o +%MEM est utilisée sur les systèmes basés sur Linux pour afficher l'outil de surveillance des processus top, trié par utilisation de la mémoire en ordre décroissant. Voici l'explication de cette commande :
- **top :** Lance l'outil de surveillance du système qui affiche en temps réel des informations sur les processus du système, l'utilisation du processeur, de la mémoire et d'autres ressources.
- **-o +%MEM :** Trie la sortie par utilisation de la mémoire, avec les processus qui consomment le plus de mémoire en haut de la liste.
Cette commande permet donc d'identifier rapidement les processus qui utilisent le plus de mémoire sur votre système.
![image](https://github.com/user-attachments/assets/d6fb30d4-2a6a-40ba-9a09-dbc06360d3b8)

# La commande **top -o +%MEM** 
- La commande vmstat (pour "virtual memory statistics") est un outil utilisé sur les systèmes Unix et Linux pour surveiller les ressources système, en particulier la mémoire virtuelle, l'utilisation du processeur, les processus, l'échange de mémoire (swap), et d'autres paramètres liés aux performances du système.

- En exécutant vmstat, vous obtenez des informations sur l'état actuel de votre système, comme :

- **Processeurs (us, sy, id, wa) :** l'utilisation du processeur par l'utilisateur, le système, l'inactivité, et l'attente d'entrées/sorties.
- **Mémoire (free, buff, cache) :** la mémoire libre, les tampons et le cache.
- **Swap (si, so) :** l'échange de mémoire, montrant les pages qui sont lues ou écrites sur le disque swap.
- **Système (in, cs) :** les interruptions et les commutateurs de contexte (changement de processus).
- **I/O (bi, bo) :** l'entrée/sortie pour les blocs (lecture et écriture).
![image](https://github.com/user-attachments/assets/0c1b216b-b1e2-409d-a087-c8c185b9fcf2)
- Dans cet exemple :
- **r :** nombre de processus en cours d'exécution.
- **b :** nombre de processus en mode "attente" (en attente d'une ressource).
- **swpd :** quantité de mémoire utilisée par le swap
- **free :** quantité de mémoire libre.
- **buff et cache :** mémoire utilisée pour les tampons et le cache.
- **si et so :** pages échangées depuis/vers le disque swap.
- **bi et bo :** nombre de blocs lus/écrits sur le disque.
- **in et cs :** nombre d'interruptions et de commutateurs de contexte.
- **us, sy, id, wa :** utilisation du processeur en mode utilisateur, système, inactif et en attente d'I/O.

# La commande **vmstat -a** 
La commande vmstat -a affiche des informations supplémentaires par rapport à la commande vmstat standard, spécifiquement sur l'allocation de la mémoire et les pages de mémoire partagée. Voici un résumé des colonnes que vous pouvez obtenir avec vmstat -a :

- **pages :** Indique des informations supplémentaires sur les pages mémoire.
- **active :** Nombre de pages actives en mémoire.
- **inactive :** Nombre de pages inactives en mémoire.
- **wired :** Nombre de pages "filtrées" en mémoire, c'est-à-dire qui ne peuvent pas être échangées sur le disque (en raison de leur utilisation par le noyau, par exemple).
- **free :** Nombre de pages libres en mémoire.
- **dirty :** Nombre de pages qui ont été modifiées mais pas encore écrites sur le disque.
- **clean :** Pages propres qui ne nécessitent pas d'écriture sur le disque.
- **cache :** Pages mises en cache par le système.
- **swapped :** Nombre de pages qui ont été échangées sur le disque.
Voici un exemple de sortie avec vmstat -a :
![image](https://github.com/user-attachments/assets/cebfad39-1913-43e6-be6b-b76067360633)

# La commande **vmstat -s** 
- La commande vmstat -S permet de spécifier l'unité de mesure utilisée pour afficher les valeurs de certaines statistiques de mémoire et d'entrée/sortie dans la sortie de vmstat. Par défaut, vmstat affiche les résultats en kilobytes (Ko), mais avec l'option -S, vous pouvez modifier l'unité de mesure.

- Voici les unités disponibles avec -S :

- **m :** Mégaoctets (MB)
- **g :** Gigaoctets (GB)
- **k :** Kilooctets (KB) (valeur par défaut)
- **t :** Téraoctets (TB)
- **p :** Pétaoctets (PB)
- **e :** Exaoctets (EB)
- **z :** Zettaoctets (ZB)
- **y :** Yottaoctets (YB)
Exemple d'utilisation de la commande :
- **vmstat -S m** : Affiche les résultats en mégaoctets.
- **vmstat -S g** : Affiche les résultats en gigaoctets.
- **vmstat -S k** : Affiche les résultats en kilooctets (valeur par défaut).
Exemple de sortie avec vmstat -S m :
![image](https://github.com/user-attachments/assets/5449d82e-f112-4e27-a52f-f5029a611a28)

- **3028 K buffer memory:** Quantité de mémoire utilisée pour la mise en tampon des entrées/sorties disque. Cette mémoire sert à stocker temporairement les données en transit entre la mémoire vive et le disque dur, améliorant ainsi les performances.

- **2118772 K swap cache:** Quantité de mémoire utilisée pour la mise en cache des pages de swap (mémoire virtuelle). Lorsque des données sont déplacées de la RAM vers le swap, une copie peut être conservée dans le swap cache pour un accès plus rapide si elles sont à nouveau nécessaires.

- **4153340 K total swap:** Taille totale de l'espace de swap disponible sur le système. Le swap est une partition du disque dur utilisée comme extension de la mémoire vive.

- **47904 K used swap:** Quantité d'espace de swap actuellement utilisée. Si cette valeur est élevée, cela indique que le système manque de mémoire vive et utilise activement le swap, ce qui peut ralentir les performances.

- **4105436 K free swap:** Quantité d'espace de swap disponible et non utilisé.

Les lignes suivantes (commençant par des nombres suivis de "non-nice user cpu ticks", "nice user cpu ticks", etc.) : Ces lignes fournissent des statistiques détaillées sur l'utilisation du CPU. "Ticks" est une unité de mesure du temps CPU.

- **11532 non-nice user cpu ticks:** Temps CPU utilisé par les processus utilisateur avec une priorité normale.
- **491 nice user cpu ticks:** Temps CPU utilisé par les processus utilisateur avec une priorité "nice" (plus basse). Les processus "nice" cèdent la priorité aux autres processus.
- **3477 system cpu ticks:** Temps CPU utilisé par le noyau du système d'exploitation pour exécuter des tâches système.
- **122357 idle cpu ticks:** Temps CPU pendant lequel le processeur était inactif.
- **819 io-wait cpu ticks:** Temps CPU pendant lequel le processeur était en attente d'opérations d'entrée/sortie (E/S), typiquement des accès disque. Une valeur élevée peut indiquer des problèmes de performance liés au disque.
- **1613 IRQ cpu ticks:** Temps CPU utilisé pour gérer les interruptions matérielles (IRQ).
- **964 softirq cpu ticks:** Temps CPU utilisé pour gérer les interruptions logicielles (softirq).
- **0 stolen cpu ticks:** Temps CPU "volé" par d'autres machines virtuelles dans un environnement virtualisé. Si cette valeur est supérieure à zéro, cela signifie que votre machine virtuelle n'a pas accès à la totalité des ressources CPU allouées.
- **2623645 pages paged in:** Nombre de pages de mémoire chargées depuis le disque vers la RAM.

- **1124719 pages paged out:** Nombre de pages de mémoire écrites depuis la RAM vers le disque (swap). Un nombre élevé de pages "paged out" indique une forte utilisation du swap.

- **888 pages swapped in:** Nombre de pages chargées depuis le swap vers la RAM.

- **12290 pages swapped out:** Nombre de pages écrites depuis la RAM vers le swap.

- **714279 interrupts:** Nombre total d'interruptions matérielles gérées par le système.

- **989882 CPU context switches:** Nombre de changements de contexte CPU. Un changement de contexte se produit lorsque le CPU passe d'un processus à un autre. Un nombre élevé de changements de contexte peut indiquer une charge importante sur le système.

- **1720118318 boot time:** Heure de démarrage du système, exprimée en secondes depuis l'Epoch Unix (1er janvier 1970).

- **5538 forks:** Nombre de processus créés (forkés) depuis le démarrage du système.






