if minikube dont wanna start do :
- sudo sysctl fs.protected_regular=0
then
- minikube start

check if all is started with :
- kubectl get all
it return all objects of minikube

you should have 2 files (index.php and lamp.yaml)

we need first to set up a secret token :
- kubectl create secret generic database --from-literal=MYSQL_ROOT_PASSWORD=nbtech --from-literal=MYSQL_DATABASE=kodekloud --from-literal=MYSQL_USER=nbtechsupport --from-literal=MYSQL_PASSWORD=nbtech --from-literal=MYSQL_HOST=mysql-service

you can verify if it has work and you can list all secrets :
- kubectl get secrets
you should have a name "database"





