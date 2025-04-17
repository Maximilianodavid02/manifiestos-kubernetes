# Proyecto Kubernetes - Minikube
### Tener instalado:
- **Docker Desktop**
- **Minikube**
- **Git**
- **Linux** en mi caso Debian **WSL**

### Clonar repositorio en bash
descarga los siguientes proyectos:
1. **repositorio de la pagina web:**
```bash
git clone https://github.com/Maximilianodavid02/static-website.git
```
2. *Repositorio de los manifiestos kubernetes:**
```bash
git clone https://github.com/Maximilianodavid02/manifiestos-kubernetes.git
```
---
### Importante si usas WSL o una VM:
-Si estás usando WSL o una máquina virtual Linux, debés mover las carpetas de los repositorios dentro del sistema de archivos de Linux para que Minikube pueda montarlas correctamente.
**Por ejemplo:**
1.copiar ls carpetas a /home/tu_usuario..
2.Asegurarse que desde el entorno linux donde correras Minikub eesten accesibles.

### Para iniciar Minikube montamos el archivo:
Desde la terminal Linux Debian WSL, donde esta tu carpeta `static-website`, ejecutar el comando en bash:
```bash
minikube start --mount --mount-string="${PWD}/static-website:/mnt/web"
```

### IMPORTANTISIMO
-Reemplazar `static-website` por la **ruta real donde tengas el index.html** si es diferente.
-Con esto montamos la carpeta local dentro de Minikube en la ruta `/mnt/web`.
---
### Verificamos Montaje
Abrir **Docker Desktop** y verificar que el volumen `/mnt/web` se haya montado dentro de minikube 
---
### Aplicamos los manifiestos de kubernetes.
Una vez parado en el proyecto donde clonaste los manifiestos, tirar el comando:
```bash
kubectl apply -R -f manifiestos-kubernetes
```
---
### A continuacion, verificamos los servicios en ejecucion con el comando:
```bash
kubectl get service
```

### Accedemos a la pagina web con el comando:
```bash
minikube service static-website-service
```
(tiene que ser el mismo nombre que tiene el metadata del service.yaml)
Con este comando comando te aparecera un http://...... apretamos CTRL y click derecho.
---
### Y LISTO 
---
ya tenemos nuestro sitio web corriendo desde un entorno kubernetes usando Minikube 









