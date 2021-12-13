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
you should have a name called  "database"

create a resource from a file or from stdin
- kubectl create -f lamp.yaml
you should get 2 services, 1 config-map, 1 deployement.apps

you can verify with :
- kubectl get all

before make a :
- kubectl get pods
to see the name of our pods, you should get something like that :
NAME                       READY   STATUS    RESTARTS   AGE
lamp-wp-5744f48f7d-ftvbt   2/2     Running   0          5m16s



then it's time to add some content to our pods inside our apache server : 
- kubectl cp $PWD/index.php lamp-wp-5744f48f7d-ftvbt:/app -c httpd-php-container

expose the service to the proxy :
- kubectl expose deployment lamp-wp --port=80 --type=NodePort

get the url where the service is runing :
- minikube service lamp-wp --url








