# Hugo shit

Resuelto el problema de cargar los datos de un formulario web a nuestra app Python.

La estrategia consiste en:
 1. Crear un formulario de Google Sheets que  incrustaremos en una página web de Hugo.
 2. Configurar el formulario para que guarde los datos en una hoja de cálculo.
 3. Crear un script Python que acceda a los datos de esa hoja de cálculo.

El script ejemplo de Google es este: 

[Python Quickstart](https://developers.google.com/sheets/api/quickstart/python "Python Quickstart")

Antes de ejecutarlo hay que seguir paso a paso esa guía. No es nada complicado. Si lo hacéis tal cual, no puede fallar:

### Paso1 
Crear un proyecto en **Google Cloud** con la cuenta del CIFP y configurar la API de Google Sheets:

https://developers.google.com/workspace/guides/create-project 

### Paso 2
Crear las **credenciales** para acceder a la **API de Google Sheet**:
https://developers.google.com/workspace/guides/create-credentials

### Paso 3
Descargar las credenciales y renombrar el fichero a `credentials.json`

### Paso 4
Lanzar el script `quickstart.py`. 
La primera ejecución crea el fichero `token.json` que permite el acceso a la hoja de cálculo.


## Mi caso
En mi caso, dispongo un formulario que pide un modelo de bici con sus características:

[Formulario alta bici](https://docs.google.com/forms/d/e/1FAIpQLSc3H8aE0YD6kwNePHEBuySMGxztKvDdMOG63OcO8aFFL2f2nQ/viewform "Form")

La hoja de cálculo en la que se vuelcan los datos del formulario es `Bicis.ods` (pero está en la nube de Google, esta es una muestra para que veáis cómo queda).

En los comentarios del script `getFormData.py`está explicado el código.

Caaaaaaan do, Maradona!!
