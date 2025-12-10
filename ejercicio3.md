# Ejercicio 3 — Creación y despliegue de un sitio Jekyll con un tema libre en Netlify

En este ejercicio se ha creado un nuevo sitio web utilizando **Jekyll** y un **tema distinto** a los usados en los ejercicios anteriores.  
El objetivo final es desplegar este sitio en **Netlify**, obteniendo una URL pública del tipo:

## Selección y descarga del tema Jekyll

Para este ejercicio se eligió un tema libre de GitHub, diferente a los anteriores.  
Los pasos realizados fueron:

1. Buscar un tema compatible con Jekyll.

2. Una vez elegido el tema, se utilizó uno de estos métodos para obtenerlo: (en mi caso el fork).
   - **Descargar ZIP**
   - **Hacer un Fork en GitHub**
   - **Clonarlo directamente**

Ejemplo usando `git clone`:

```bash
git clone https://github.com/autor/tema-jekyll-ejemplo.git
cd tema-jekyll-ejemplo

```
![foto](/assets/img/2__1.png/)

## Preparación del entorno Jekyll

Como en los ejercicios anteriores se utilizó un sistema Debian en el que se hizo lo siguiente:

- Instalación de dependencias

```bash
sudo apt update
sudo apt install -y ruby-full build-essential zlib1g-dev git

```

- Instalación de Jekyll y Bundler

```bash
gem install jekyll bundler

```
## Instalación del tema, comprensión del mismo y comprobación local

Una vez descargado el tema, se instaló con el comando:

```bash
bundle install

```
Después se probó localmente:

```bash
bundle exec jekyll serve

```
Esta fase es importante para asegurarse de:

- que el tema funciona bien,

- que no faltan dependencias,

- que las rutas o layouts no dan error.

Pero algo muy importante es que para yo poder probarle adecuadamente antes me tuve que enterar de como funcionaba leyendome el archivo README.md donde explica el funcionamiento del tema.

![foto](/assets/img/2__2.png/)

## Personalización del sitio

### Edición del archivo config.yml

Dentro de este archivo se cambiaron:

- Título del sitio (title).

- Descripción (description).

- Autor (author).

### Creación de nuevas páginas o posts
Como en el ejercicio anterior cree nuevos post basandome en el funcionamiento del tema.

![foto](/assets/img/2__3.png/)

## Y ya por ultimo la subida del proyecto a github y despues su despliegue del sitio en Netlify

Con los comandos de siempre lo subí todo al github:

```bash
git add .
git commit -m "Ejercicio 3 - Sitio Jekyll con tema libre"
git push 

```
Y una vez subido al github ya estaba todo listo para poderlo desplegar en Netlify.

### Crear el sitio en Netlify

- Entrar en la páguina oficial de Netlify.

- Pulsar New site from Git.

- Elegir GitHub.

- Seleccionar el repositorio del ejercicio 3.

### Configurar el build

Para poder desplegarlo correctamente sin que de un error, primero hay que configurar una serie de parametros antes:

- En el build comand poner : bundle exec jekyll build.

- Y en el public directory poner: _site.

### Pruebas finales 

Lo más seguro es que de algun error al iniciar asi que por ello dentro de la páguina hay una IA que te lee los errores que has tenido y te da soluciones para los mismos, hay que estar todo el rato iniciandolo hasta que porfin no te de ningun error y eso significara que por fin se desplego correcamente y aparecera un mensaje que diga "Publicado con éxito".

![foto](/assets/img/2__4.png/)