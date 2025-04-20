
## 1. Instalar Docker Desktop

## 2. Clonar repositorio

Descargar el repositorio y una vez clonado ingresar a la carpeta `sysreptor`

```
git clone https://github.com/BelisarioGM/Sysreptor.git

cd /Sysreptor
```

## 3. Compilar el Docker

Desde la carpeta `Sysreptor`, abrir una consola y ejecutar:

```
docker compose up --build
```

- **Nota**: En caso de que no funcionen las credenciales `admin:admin`, se debe ejecutar un paso adicional, el cual consiste en entrar a la base de datos y agregar manualmente las credenciales que no fueron creadas en la base de datos al momento de compilar el `Docker Compose.` 

```
docker exec -it sysreptor-app bash
```

```
python manage.py shell
```

```
from django.contrib.auth import get_user_model
User = get_user_model()
User.objects.create_superuser("admin", "", "admin")
exit()
```

# Update !!

El archivo `docker-compose.yml` trae por defecto la ultima versión estable del `sysreptor`, por lo que mucha veces se verán notificaciones diciéndonos que hay nuevas actualizaciones.

En caso de que se quiera hacer una actualización se debe ejecutar desde la carpeta `/Sysreptor:` 

```
docker compose pull
docker compose up -d
```

y de esta forma actualizará a la versión estable mas reciente disponible.
