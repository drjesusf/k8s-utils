# k8s-utils

# Install Minikube
minikube start

# Get Namespaces
kubectl get namespaces

# Create new namespace
kubectl create namespace <namespace-name>

# Para btener mas detalle sobre el namespace
kubectl describe namespace <namespace-name>

### Docker - Crear una imagen para subirlo a k8s
Se deberá crear un archivo Dockerfile

# Construir la imagen y subirlo al entorno local de Docker
docker build -t <aplication-name>:latest .
docker images

# - Si quiero publicar la app en puerto 8085
docker run -d -p 8085:8080 --name newapi newapi:1.4

###### ####### Docker en minikube ###### #######

# Para usar el docker de minikube
minikube docker-env

# Ejecutar el comando que se indica
& minikube -p minikube docker-env --shell powershell | Invoke-Expression

# Hacer el build del Dockerfile para q se cree la imagen dentro de minikube
docker build -t <aplication-name>:latest .
docker images 


###### ####### k8s deploy ###### #######
# Aplicar el archivo de despliegue
kubectl apply -f deployment.yaml

# Aplicar el archivo de servicio
kubectl apply -f service.yaml

# Publicar el pod en un puerto que se pueda acceder desde local| 
kubectl port-forward <application-name> 8085:8080