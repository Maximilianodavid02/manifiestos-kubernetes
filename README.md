# Proyecto Kubernetes - Minikube
### Tener instalado:
- **Docker Desktop**
- **Minikube**
- **Git**
- **Linux** en mi caso Debian **WSL**

###Clonar repositorio en bash
-**repositorio de la pagina web:**
git clone https://github.com/Maximilianodavid02/static-website.git
--*Repositorio de los manifiestos kubernetes:**
git clone https://github.com/Maximilianodavid02/manifiestos-kubernetes.git

###Para iniciar Minikube montamos el archivo:**
Desde la terminal Linux Debian WSL, donde esta tu carpeta 'static-website', ejecutar el comando en bash:
'''minikube start --mount --mount-string="/home/maxi/static-website:/mnt/web"'''

**Eso si IMPORTANTISIMO**
-Reemplazar 'static-website' por la **ruta real donde tengas el index.html** si es diferente.
-Con esto montamos la carpeta local dentro de Minikube en la ruta '/mnt/web'.

###Verificamos Montaje
Abrir **Docker Desktop** y verificar que el volumen '/mnt/web' se haya montado dentro de minikube 

###Aplicamos los manifiestos de kubernetes.
Una vez parado en el proyecto donde clonaste los manifiestos, tirar el comando:
'''kubectl apply -R -f manifiestos-kubernetes

###A continuacion, verificamos los servicios en ejecucion con el comando:
'''kubectl get service'''

###Accedemos a la pagina web con el comando:
'''minikube service static-website-service (tiene que ser el mismo nombre que tiene el metadata del service.yaml)'''
con este comando comando te aparecera un http://...... apretamos CTRL y click derecho.
**Y LISTO** ya tenemos nuestro sitio web corriendo desde un entorno kubernetes usando Minikube 









