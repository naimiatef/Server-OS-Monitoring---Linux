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
![image](https://github.com/user-attachments/assets/55556f5a-425c-4f3f-82f0-bc86a8de1c85)


