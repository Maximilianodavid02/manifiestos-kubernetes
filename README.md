# Proyecto Kubernetes - Minikube

Pasos para Reproducir el Proyecto
-Clonar el Repositorio
Clona el repositorio del proyecto con el siguiente comando:
git clone https://github.com/ewojjowe/static-website.git
cd static-website
-Iniciar el Clúster de Minikube
Inicia Minikube para crear un entorno Kubernetes local:
minikube start
-Crear el Volumen Persistente
Asegurar de que el volumen persistente esté creado. Este volumen se utilizará para montar los archivos HTML y CSS dentro del contenedor Nginx.
kubectl apply -f pvc.yaml
-Desplegar el Contenedor Nginx
Aplicae el manifiesto para desplegar el contenedor Nginx y montar el volumen persistente en el directorio /usr/share/nginx/html:
con el comando:
kubectl apply -f deployment.yaml
Este manifiesto crea un contenedor Nginx que servirá el contenido del sitio web estático desde el volumen persistente.
-Exponer el Servicio
Para exponer el sitio web fuera del clúster, crea un servicio de tipo NodePort con el siguiente comando:
kubectl apply -f service.yaml
-Verificar el Despliegue
Verificar que el pod del sitio web esté en ejecución:
kubectl get pods
Deberíamos ver algo como esto:
sql
NAME                                     READY   STATUS    RESTARTS   AGE
static-website-76d4cf8569-wnrzq           1/1     Running   0          5m
-Acceder al Sitio Web
Obtén la IP de Minikube y el puerto del NodePort para acceder al sitio web:
minikube ip
Accede al sitio web con la IP y el puerto:
http://<minikube-ip>:<node-port>
-Verificar los Archivos del Sitio Web
Para verificar que el volumen se montó correctamente y los archivos del sitio web están disponibles, accede al pod y revisa el directorio:
kubectl exec -it static-website-76d4cf8569-wnrzq -- ls /usr/share/nginx/html
Deberías ver los archivos del sitio web, como index.html y style.css.
-Detener el Clúster
Cuando termines, puedes detener Minikube:
minikube stop

deployment.yaml: Manifiesto de Kubernetes para el despliegue del contenedor Nginx con el volumen persistente.
service.yaml: Manifiesto de Kubernetes para exponer el servicio como un NodePort.
static-website/: Contiene los archivos del sitio web estático (por ejemplo, index.html y style.css).
pvc.yaml: Manifiesto de Kubernetes para crear un volumen persistente (PVC).



