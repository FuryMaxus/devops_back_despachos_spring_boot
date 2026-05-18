### Repositorio: MICROSERVICIO DESPACHO

# Microservicio de Despacho 

## 1. Descripción
Módulo desacoplado para la gestión logística, desplegado en instancia EC2 independiente.

## 2. Características Técnicas
* **Dockerfile:** Optimizado para bajo consumo de recursos y seguridad (usuario nginx/spring).
* **Puerto:** Operación en el puerto `8081` para evitar colisiones y permitir integración con el Front.
* **Orquestación:** Docker Compose habilitado para despliegue conjunto de App + DB.

## 3. Automatización (Zero Trust)
Pipeline de despliegue continuo que utiliza **AWS Systems Manager** para actualizar contenedores de forma segura, manteniendo los Security Groups cerrados (sin puerto 22).

## 4. Ejecución Local
Prepare su entorno local creando un archivo `.env` con:
* `DB_NAME=despacho_db`
* `DB_USER=root`
* `DB_PASSWORD=su_password`
* `REGISTRY=local`

Luego ejecute:
```bash
docker compose up -d
