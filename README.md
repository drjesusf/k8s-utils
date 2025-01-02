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

# Para usar el docker de minikube
# Ejecutar el comando que se indica
# Hacer el build del Dockerfile para q se cree la imagen dentro de minikube
minikube docker-env
docker images 
docker build -t <aplication-name>:latest .

# Aplicar el archivo de despliegue
kubectl apply -f deployment.yaml

# Aplicar el archivo de servicio
kubectl apply -f service.yaml
