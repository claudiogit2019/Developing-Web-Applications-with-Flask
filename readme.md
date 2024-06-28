
# Desarrollo de aplicaciones web con Flask

## Introducción a Flask

    Explicar qué es Flask y sus beneficios en comparación con otros marcos

    Configurar un entorno de desarrollo para Flask

    Creación de una aplicación básica de Flask

    Flask es un marco de desarrollo web ligero que puede ofrecer aplicaciones complejas con un código mínimo. Aquí aprenderá qué es Flask, sus beneficios y sus casos de uso.

    Para obtener una introducción básica, lea los siguientes artículos para obtener una descripción general rápida de Flask y una de sus integraciones, Flask-SQLAlchemy.

🔗 [Todo lo que necesitas saber sobre Flask para principiantes](https://www.mygreatlearning.com/blog/everything-you-need-to-know-about-flask-for-beginners/)

🔗 [Integración de Flask con SQLAlchemy](https://www.section.io/engineering-education/flask-database-integration-with-sqlalchemy/)

Flask es un microframework web que está escrito en Python. La documentación establece múltiples beneficios de usar Flask, a saber:

Su ligereza, facilidad de extensión en el desarrollo e integraciones con otras librerías
Su pequeña curva de aprendizaje
Su legibilidad

## Instalación de Flask

Ahora que sabes un poco más sobre Flask, ¡es hora de empezar a desarrollar! Para empezar, vamos a crear un entorno de desarrollo para la aplicación. El entorno virtual que crearemos contendrá un entorno de Python autónomo con su propia instalación de Python, pip (administrador de paquetes de Python) y otros archivos necesarios. Esto le permite instalar y administrar paquetes de Python específicos de este proyecto o entorno sin afectar a la instalación de Python en todo el sistema ni a otros proyectos. Dado que Flask está codificado en Python, los usuarios familiarizados con Python pueden encontrar estos pasos familiares.

Si no lo ha hecho, instale Python 3 y su administrador de paquetes "pip".

Para los usuarios de Windows, puede hacerlo en el [sitio web oficial de Python](https://www.python.org/downloads/).

Para los usuarios de Mac, ingrese el siguiente comando en su terminal.

En primer lugar, crea una nueva carpeta para esta campaña. En esta nueva carpeta, cree una carpeta denominada Quest1. En Quest1, cree una carpeta llamada app y un archivo llamado requirements.txt. En la carpeta de la aplicación, cree un archivo denominado app.py. Ahora debería tener una estructura de directorios de archivos similar a la siguiente:

![directorio](imagen\flask1.png)

A continuación, abra un terminal en el directorio Quest1 y ejecute el siguiente comando* para crear un entorno virtual para nuestra búsqueda. El módulo venv es un módulo integrado en Python que se utiliza para crear entornos virtuales. Una vez que se ejecute el comando, verá la carpeta venv creada. Nota: Si el resultado del comando indica que Python no está instalado, puede reemplazar python3 con python en su lugar.

            python3 -m venv ./venv/

A continuación, usaremos el siguiente comando para activar el entorno virtual que acabamos de crear. Una vez que se ejecute el comando, notará que el mensaje en su terminal cambia, que ahora incluye (venv). Esto indica que ahora está trabajando en el entorno virtual.

Para usuarios de Windows

            .\venv\Scripts\activate.bat

A continuación, introdúzcalo en el archivo requirements.txt.

            Flask

A continuación, ejecute el siguiente código en su terminal para instalar el paquete necesario que enumeramos en el archivo requirements.txt.

            pip3 install -r requirements.txt

## Creación de la primera aplicación

En primer lugar, abra app.py en su editor de código e ingrese esta línea.

        from flask import Flask

Esta línea importa el módulo Flask de la biblioteca Flask que usará más adelante.

A continuación, inicialice su aplicación con esta línea. Esto crea una aplicación Flask en la que puede incluir funciones.

        app = Flask(__name__)

Ahora, ¡vamos a crear la primera ruta! En un sitio web típico, su URL o enlace se vería así: https://www.examplewebsite.com/page . En este caso, la ruta se define como "/". Intentemos replicar eso ingresando este fragmento de código a continuación.

        @app.route('/')
        def hello_world():
            return 'Hello World!'

Esto crea una ruta en "/" que devolverá el texto "¡Hola mundo!".

Y, por último, ejecutemos la aplicación con el siguiente código.

        if __name__ == '__main__':
            app.run()

El código final en app.py debería tener este aspecto.

![app.py](imagen\flask2.png)

Guarde el archivo. En su terminal, cambie el directorio de trabajo actual a app y ejecute app.py con este comando en su terminal.

                python3 app.py

A continuación, abra http://localhost:5000/

Debería ver su sitio web alojado en su computadora y el mensaje "¡Hola mundo!".

![hola ](imagen\flask3.jfif)

## Hospedaje público de la aplicación

Ahora que tienes Flask instalado y has creado tu primera aplicación, ¡vamos a intentar alojarla para que sea accesible a otros!

Usaremos [Vercel](https://vercel.com/), un servicio gratuito de alojamiento de aplicaciones que brinda soporte para Flask.

En primer lugar, crea una cuenta de Vercel [aquí](https://vercel.com/login) si no tienes una cuenta. Su nombre de usuario para Vercel debe ser el mismo o muy similar a su nombre de usuario de StackUp. Puede cambiar su nombre de usuario en la Configuración de la cuenta personal.

Después de crear su cuenta, vuelva a Visual Studio Code y ejecute los siguientes comandos en su terminal para instalar la utilidad Vercel CLI. Esto requiere npm, que se instala junto con [Node.js](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

                npm i -g vercel

A continuación, ejecute el siguiente comando en el directorio Quest1.

                vercel

A continuación, cree el archivo vercel.json en el directorio Quest1 con el siguiente contenido.

                {
                "version": 2,
                "builds": [
                {
                        "src": "app/app.py",
                        "use": "@vercel/python"
                }
                ],
                "routes": [
                {
                        "src": "/(.*)",
                        "dest": "app/app.py"
                }
                ]
                }


A continuación, queremos asegurarnos de que nuestra URL de vista previa pueda ser vista por otros. En su navegador, diríjase a Vercel e inicie sesión. Seleccione el proyecto flask-quest1 que creó anteriormente. Vaya a la pestaña Configuración. Seleccione Protección de implementación y deshabilite la autenticación de Vercel. Asegúrese de hacer clic en Guardar.

![publico](imagen\flask4.jfif)

## captura de pantalla

![publico](imagen\flask5.png)

## enlace web

https://flask-quest1-7ip9ejq8j-antonio-claudio-ortizs-projects.vercel.app/

