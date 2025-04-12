# Proyecto Kubernetes - Minikube

Este proyecto está diseñado para crear un entorno Kubernetes en Minikube para desplegar una aplicación web estática personalizada. A continuación se describen los pasos seguidos y las herramientas utilizadas para configurar el entorno y desplegar la aplicación.

## Contenido

- [Requisitos previos](#requisitos-previos)
- [Pasos para reproducir el entorno](#pasos-para-reproducir-el-entorno)
- [Estructura de Carpetas](#estructura-de-carpetas)
- [Git y GitHub](#git-y-github)
- [Comandos utilizados](#comandos-utilizados)
- [Detalles adicionales](#detalles-adicionales)

---

## Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes programas:

- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [Debian WSL](https://www.microsoft.com/en-us/p/debian/9msvkpqv3x3h)
- [Visual Studio Code](https://code.visualstudio.com/)

## Pasos para reproducir el entorno

1. **Instalar Minikube y Docker Desktop**: Asegúrate de tener ambos instalados y funcionando correctamente. Si no los tienes, puedes seguir las guías oficiales para su instalación.
   
2. **Clonar el repositorio**:
   
   Clona este repositorio en tu máquina local utilizando el siguiente comando:
   ```bash
   git clone https://github.com/Maxi/README.git
   cd README
una vez clonado el repositorio crear el cluster del minikube
-minikubestart
