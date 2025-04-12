# Proyecto Kubernetes - Minikube

Este proyecto está diseñado para crear un entorno Kubernetes en Minikube para desplegar una aplicación web estática personalizada. A continuación se describen los pasos seguidos y las herramientas utilizadas para configurar el entorno y desplegar la aplicación.

Tenemos el repositorio static-website con el fork clonada y personalizado el html y css
Y el repositorio llamado manifiestos-kubernetes donde se encuentra el entorno kubernetes con los deployment

Entorno del trabajo fue Minikube, Docker, Visual studio Code, GitHub, use debian en WSL2.
los pasos del despliegue :
clonar repo, aplicar los archivos .yaml de kubernetes y la la verificacion con kubectl 
algunos comandos utilizados fueron kubectl, git, docker, etc
hice fork a la URL que especficaba en el pdf de la actividad , lo personalize en visual studio code a mi gusto, y lo comitie, como:
1- navego la carpeta de mi repositorio local 
2- hago un git status para revisar el estado del repositoriouna vez parado en esa carpeta
3- agrego los cambios al area de staging com un git add .
4- creo un commit con un mensaje claro de lo que hice, con el mando git commit -m "Mensaje"
5- subo los cambios a mi repositorio con el comando git push origin main

Despues creo los manifiestos de kubernetes 
-1 me voy a la carpeta de manifiestos-kubernetes local en la terminal de gitbash
-2 una vez en la carpeta, creo los manifistos de kubernetes, los hago dentro de la carpeta de manifiestos-kuberntes y abro visual sutdio code para hacer los yaml, que son: depolyment.yaml, pv.yaml, pvc.yaml y service.yaml
 Despues creo y configuro el cluster en Minikube con Minikube start , despues verifico que este corriendo con minikube status, despues verifico el entorno de kubernetes con kubectl get nodes
despues de haber creado creado todo eso aplico los mos manifiestos de kubernetes con el comando kubectl apply -f /y la tura a mi manifiesto kubernetes/.yaml
despues verifico que el pod este corriendo con kubectl get pods, verifico el servicio con kubectl get services
y Despues acceso a la aplicacion desde el navegador con minikube IP y me devuelve una IP y la pego en el navegador




