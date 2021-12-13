Dans ce document nous allons retrouver les grandes étapes de notre mise en place d'une stack LAMP sur Kubernetes via minikube, ainsi que quelques problèmes auxquels nous avons été confrontés.

Installation :

    Premièrement, nous allons installer Minikube. Ce logiciel est un outil permettant l'éxecution locale de Kubernetes.

    Après avoir installé Minikube, nous allons le configurer avec deux fichiers importants "index.php" et "lamp.yaml". 
    Pour cela, nous allons d'abord créer un token secret qui nous permettra de générer une base de données.
    Puis nous allons créer le fichier .yaml, où on peut voir sa configuration dans la partie "feature/working-one-pod".
    Après cela, nous allons nous occuper des pods en installant dessus le serveur apache ainsi que le proxy. (Un pod est un groupe d'un ou plusieurs conteneurs).

    Après tout cela installé nous récupérons l'url où le service tourne pour constater la réussite de la mise en place LAMP.

Problèmes majeurs :

    Nous avons rencontrés quelques problèmes pendant la mise en place de la stack :
    
    - la documentation pour simplement installer kubernetes c'est trouvait être très peu explicites et nous avons du chercher pendant plusieurs heures pour réussir cette installation.

    - La configuration du fichier "lamp.yaml" nous a compliqué la tâche car nous ne trouvions pas la bonne configuration.

    - Le déploiement de Lamp, ou encore le manque de documentation ne nous a pas aidés

    - Problème de connexion à la base de données. En effet, nous n'avions pas compris que si on mettait nos deux services sur le même pod et que le passage par localhost était nécessaire au lieu de (PRECISION).