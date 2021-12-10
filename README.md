# Hugo shit

Resuelto el problema de cargar los datos de un formulario web a nuestra app Python.

La estrategia consiste en:
 1. Crear un formulario de Google Sheets que  incrustaremos en una página web de Hugo.
 2. Configurar el formulario para que guarde los datos en una hoja de cálculo.
 3. Crear un script Python que acceda a los datos de esa hoja de cálculo.

El script ejemplo de Google es este: 

[Python Quickstart](https://developers.google.com/sheets/api/quickstart/python "Python Quickstart")

Antes de ejecutarlo hay que seguir paso a paso esa guía. No es nada complicado. Si lo haces tal cual, no puede fallar:

### Paso 1
Crea un proyecto en **Google Cloud** con la cuenta del CIFP y configurar la API de Google Sheets:

https://developers.google.com/workspace/guides/create-project 

### Paso 2
Crea las **credenciales** para acceder a la **API de Google Sheet**:
https://developers.google.com/workspace/guides/create-credentials

### Paso 3
Descarga las credenciales y renombra el fichero a `credentials.json`

### Paso 4
Crea un entorno virtual en el proyecto

`python3.8 -m venv venv`

y actívalo:

`source venv/bin/activate`

Instala las dependencias a las librerias de Google que indica la guía:

`pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib`

Obtén el `id` de la hoja de cálculo y especifica el rango de valores a solicitar siguiendo la notación `A1`. Todos estos detalles están en comentarios en mi código.

Lanza el script `quickstart.py`. 

La primera ejecución crea el fichero `token.json` que permite el acceso a la hoja de cálculo.

### API 
Selecciona las funciones de la API Rest de Google Sheets que más se adecuen a tu flujo de trabajo:
https://developers.google.com/sheets/api/reference/rest/

Fíjate en la documentación que parámetros recogen y qué objeto devuelven.

## Mi caso
En mi caso, dispongo un formulario que permite introducir un modelo de bici con sus características:

[Formulario alta bici](https://docs.google.com/forms/d/e/1FAIpQLSc3H8aE0YD6kwNePHEBuySMGxztKvDdMOG63OcO8aFFL2f2nQ/viewform "Form")

La hoja de cálculo en la que se vuelcan los datos del formulario es `Bicis.ods` (está en la nube de Google, esta es sólo una muestra para que veas la disposición de los datos).

En los comentarios del script `getFormData.py`está explicado el código.

Caaaaaaan do, Maradona!!

![Diegol](./resources/diegol.png "https://www.instagram.com/religionemonoteistica/")
