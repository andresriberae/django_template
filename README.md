# Django Template

Aplicación web desarrollada con Django y Tailwind CSS. El proyecto utiliza una arquitectura modular basada en aplicaciones Django y una estructura independiente para la gestión de estilos y recursos estáticos.

## Tecnologías

| Tecnología | Versión |
| --- | --- |
| Python | 3.14+ |
| Django | 6.1 |

## Requisitos

Antes de iniciar el proyecto, es necesario contar con:

* Python 3.14 o superior
* Git
* Entorno virtual de Python

## Instalación

### 1. Clonar el repositorio

```bash
git clone <URL_DEL_REPOSITORIO>
cd repo_dif
```
### 2. Crear y activar el entorno virtual

Crear el entorno:

```bash
python -m venv venv
```

Activarlo en macOS/Linux:

```bash
source venv/bin/activate
```

Activarlo en Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Activarlo en Git Bash (Windows):

```bash
source venv/Scripts/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Configurar variables de entorno

Crea tu archivo local `.env` a partir del ejemplo.

En macOS/Linux:

```bash
cp .env.example .env
```

En Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

Edita `.env` y establece una clave secreta propia:

```env
DEBUG=True
SECRET_KEY=pega_aqui_tu_clave_secreta
ALLOWED_HOSTS=127.0.0.1,localhost
```

Puedes generar una clave segura con:

```bash
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```

### 5. Aplicar migraciones

```bash
python manage.py migrate
```

### 6. Ejecutar el servidor

```bash
python manage.py runserver
```

La aplicación estará disponible en [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

Si el puerto `8000` está ocupado, usa otro:

```bash
python manage.py runserver 8001
```

## Estructura del proyecto

```text
django_template/
│
├── core/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
│
├── templates/
│   └── home.html
│
├── venv/
│
├── .env.example
├── .gitignore
├── manage.py
├── requirements.txt
└── README.md
```

## Comandos principales

### Django

Verificar la configuración del proyecto:

```bash
python manage.py check
```

Ejecutar el servidor:

```bash
python manage.py runserver
```

Crear migraciones:

```bash
python manage.py makemigrations
```

Aplicar migraciones:

```bash
python manage.py migrate
```

Crear un superusuario:

```bash
python manage.py createsuperuser
```

## Variables de entorno

No subas secretos al repositorio. Asegúrate de que `.gitignore` incluya:

```gitignore
venv/
__pycache__/
*.py[cod]
.env
```

`.env.example` sí debe versionarse y no debe incluir claves reales:

```env
DEBUG=True
SECRET_KEY=
ALLOWED_HOSTS=127.0.0.1,localhost
```

## Estado actual

- Proyecto Django inicializado en `core`.
- Configuración preparada para usar variables de entorno.
- Estructura lista para crear aplicaciones, vistas, modelos y plantillas.