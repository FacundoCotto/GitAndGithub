_Facundo Cotto, Ignacio Correa , Pia Schiavone, Bruno Crizul_

Acerca de GitHub

GitHub es una plataforma basada en la nube donde puedes almacenar, compartir y trabajar junto con otros usuarios para escribir código.

Almacenar tu código en un "repositorio" en GitHub te permite lo siguiente: _ Presentar o compartir el trabajo. _ Seguir y administrar los cambios en el código a lo largo del tiempo.

Dejar que otros usuarios revisen el código y realicen sugerencias para mejorarlo.
_Colaborar_ en un proyecto compartido, sin preocuparse de que los cambios afectarán al trabajo de los colaboradores antes de que esté listo para integrarlos.
El trabajo colaborativo, una de las características fundamentales de GitHub, es posible gracias al software de código abierto Git, en el que se basa GitHub.

Acerca de Git

Git es un sistema de control de versiones que realiza un seguimiento de los cambios en los archivos. Git es especialmente útil cuando un grupo de personas y tú estáis haciendo cambios en los mismos archivos al mismo tiempo.

Normalmente, para hacerlo en un flujo de trabajo basado en Git, harías lo siguiente: _ Crear una rama a partir de la copia principal de archivos en los que tú (y tus colaboradores) estáis trabajando. _ Realizar modificaciones en los archivos de forma independiente y segura en tu propia rama personal.

```bash
Deja que Git fusione de forma inteligente tus cambios específicos de nuevo a la copia principal de los archivos, de modo que no interfieran con las actualizaciones realizadas por otras personas.
Dejar que Git realice un seguimiento de tus cambios y los de otras personas, por lo que todos siguen trabajando en la versión más actualizada del proyecto.
Para probar Git personalmente, consulta Comenzar con Git.
```

_¿Cómo funcionan Git y GitHub de manera conjunta?_

**Al cargar archivos en GitHub, los almacenarás en un "repositorio de Git". Esto significa que al realizar cambios (o "confirmaciones") en los archivos de GitHub, Git se iniciará automáticamente para realizar el seguimiento de los cambios y administrarlos.**

Hay muchas acciones relacionadas con Git que puedes completar en GitHub directamente en el navegador, como crear un repositorio de Git, crear ramas y cargar y editar archivos.

Pero la mayoría de los usuarios trabajan en sus archivos localmente (en su propio ordenador), luego sincronizan continuamente estos cambios locales y todos los datos de Git relacionados, con el repositorio central "remoto" en GitHub. Hay muchas herramientas que puede usar para hacerlo, como GitHub Escritorio.

Cuando empieces a colaborar con otros y todos necesitéis trabajar en el mismo repositorio al mismo tiempo, haréis lo siguiente continuamente:

        *Extrae* todos los cambios más recientes realizados por tus colaboradores del repositorio remoto en GitHub.
        *Insertar* sus propios cambios en el mismo repositorio remoto en GitHub.

Git determina cómo combinar inteligentemente este flujo de cambios y GitHub te ayuda a administrarlo mediante características como las "solicitudes de cambios".
