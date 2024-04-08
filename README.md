
---
<div style="background-image: url(https://media3.giphy.com/media/wwg1suUiTbCY8H8vIA/giphy.gif?cid=ecf05e47hfu84pmh8vk2mo5wohm7vxo4hcx1gu3ye1664zcy&ep=v1_gifs_search&rid=giphy.gif&ct=g); display: flex; justify-content: center;">

# Sicer Andres Brito Gutierrez 🧑‍💻 Skeleton-4-Capas-8.0 <img src="https://api.nuget.org/v3-flatcontainer/microsoft.entityframeworkcore/8.0.0-preview.6.23329.4/icon" alt="img" style="width: 38px;">
</div>


<div style="display: flex; justify-content: center;">

## Esqueleto BackEnd .Net 8.0 hecho por [Sicer Brito 🧑‍💻](https://github.com/SicerBrito)
</div>





# Índice 📖
Esqueleto con la estructura base para el desarrollo BackEnd con .Net 8.0, sus Snippets para realizarlo y su respectiva documentación

- [Documentación](#documentación) 📄
    - [Estructura del Proyecto](#estructura-del-proyecto) 🏗️
    - [Terminal](#terminal) ⚙️
        - [Estructura Base](#estructura-base) 🚧
        - [Referencias](#referencias) 🔗
    - [Gestión de Datos](#gestión-de-datos) 📇
        - [Instalación de Paquetes](#instalación-de-paquetes) ⏬
            - [Dominio](#dominio) 📂
            - [Persistencia](#persistencia) 📂
            - [API](#api) 📂
        - [Migraciones](#migraciones) ✈️
            - [Crear](#crear) 🔧
            - [Actualizar](#actualizar) 🔧
        - [Visualización de posibles errores](#visualización-de-posibles-errores) ⁉️
    - [Construcción del Código Base](#construcción-del-código-base)


---
# Documentación  
Mi objetivo con este proyecto es centrarme en la eficiencia del desarrollo BackEnd y hacer este proceso menos tedioso y corto. Espero que mi contribución sea lo más efectiva posible para todo aquel que desee realizar un proyecto similar con esta estructura 📄  

## Estructura del Proyecto
Estas son las carpetas de configuración las cuales vamos a utilizar para nuestros proyectos BackEnd

 - 📂 En Dominio  
        Aquí se crean las tablas que representan la Base de Datos y van a estar ubicadas las carpetas de Entities e Interfaces

 - 📂 En Persistencia  
        Aquí se crea la instancia de conexión a la Base de Datos y van a estar ubicadas las carpetas de Data, Configuration, Archivo Context (DbAppContext) y Migrations

 - 📂 En Aplicacion  
        Aquí se crea la inyección de dependencias para la comunicación con la API y van a estar ubicadas las carpetas de UnitOfWork y Repository
        
 - 📂 En API  
        Aquí se crean clases encargadas de recibir peticiones de los clientes y van a estar ubicadas las carpetas de Controllers, Dtos, Extensions, Helpers, Profiles, Contenedor de dependecias (program.cs) y Extensions. Además se crean clases encargadas de la configuración de los archivos JWT (JSON Web Tokens) para la seguridad de nuestro proyecto


---

   <img src="https://github.com/SicerBrito/NuevaEstructura/raw/main/Img/Relaciones.PNG" alt="Relaciones" style="width: 3000px;">

---





## Terminal

 - ### Estructura Base
    
    ---
    - Instala la herramienta "dotnet-ef" globalmente para trabajar con Entity Framework Core 🚧🔧
        ```
        dotnet tool install --global dotnet-ef 
        ```

    
    ---
    - Lista las herramientas globales instaladas en .NET 🚧🔧
        ```
        dotnet tool list -g
        ```

    ---
    - En caso de no estar desactualizado se puede actualizar mediante este comando 🚧🔧
        ```
        dotnet tool update --global dotnet-ef
        ```
    ---
    - Crea una nueva solución de .NET  
    Una solución (.sln) se refiere a un archivo que actúa como un contenedor para organizar y administrar proyectos relacionados en un entorno de desarrollo de .NET 🚧🔧
        ```
        dotnet new sln
        ```

    ---
    - Crea un nuevo proyecto de biblioteca de clases utilizando .NET Core y lo guarda en la carpeta "Dominio". Las bibliotecas de clases son conjuntos de código reutilizable que pueden ser referenciados y utilizados en otros proyectos .NET Core. En este caso, el nombre "Dominio" sugiere que esta biblioteca podría contener clases y lógica relacionada con el dominio central de la aplicación, como modelos y reglas de negocio 🚧🔧
        ```
        dotnet new classlib -o Dominio
        ```

    ---
    - Crea un nuevo proyecto de biblioteca de clases utilizando .NET Core y lo guarda en la carpeta "Persistencia". Las bibliotecas de clases son conjuntos de código reutilizable que pueden ser referenciados y utilizados en otros proyectos .NET Core. En este caso, el nombre "Persistencia" sugiere que esta biblioteca podría contener clases y lógica relacionada con el acceso y la manipulación de datos, como el uso de bases de datos y almacenamiento persistente 🚧🔧
        ```
        dotnet new classlib -o Persistencia
        ```
    ---
    - Crea un nuevo proyecto de biblioteca de clases utilizando .NET Core y lo guarda en la carpeta "Aplicacion". Las bibliotecas de clases son conjuntos de código reutilizable que pueden ser referenciados y utilizados en otros proyectos .NET Core. En este caso, el nombre "Aplicacion" sugiere que esta biblioteca podría contener clases y lógica relacionada con la capa de aplicación, como la implementación de casos de uso y la interacción con la interfaz de usuario 🚧🔧
        ```
        dotnet new classlib -o Aplicacion
        ```

    ---
    - Crea un nuevo proyecto de API web utilizando .NET Core y lo guarda en la carpeta "API". Este comando establece las bases para crear una API utilizando el framework .NET Core, que puede ser utilizada para exponer servicios a través de HTTP 🚧🔧
        ```
        dotnet new webapi -o API
        ```

    ---
    - Agrega el proyecto ubicado en la carpeta "Dominio" al archivo de solución actual de .NET Core. Esto permite incluir el proyecto "Dominio" dentro de la solución y facilita la gestión de múltiples proyectos en un mismo contexto de desarrollo. Es útil cuando se tiene una solución que consta de varios proyectos y se quiere mantener todo organizado en una estructura de solución 🚧🔧
        ```
        dotnet sln add Dominio/
        ```

    ---
    - Agrega el proyecto ubicado en la carpeta "Persistencia" al archivo de solución actual de .NET Core. Esto permite incluir el proyecto "Persistencia" dentro de la solución y facilita la gestión de múltiples proyectos en un mismo contexto de desarrollo. Es útil cuando se tiene una solución que consta de varios proyectos y se quiere mantener todo organizado en una estructura de solución 🚧🔧
        ```
        dotnet sln add Persistencia/
        ```

    ---
    - Agrega el proyecto ubicado en la carpeta "Aplicacion" al archivo de solución actual de .NET Core. Esto permite incluir el proyecto "Aplicacion" dentro de la solución y facilita la gestión de múltiples proyectos en un mismo contexto de desarrollo. Es útil cuando se tiene una solución que consta de varios proyectos y se quiere mantener todo organizado en una estructura de solución 🚧🔧
        ```
        dotnet sln add Aplicacion/
        ```

    ---
    - Agrega el proyecto ubicado en la carpeta "API" al archivo de solución actual de .NET Core. Esto permite incluir el proyecto "API" dentro de la solución y facilita la gestión de múltiples proyectos en un mismo contexto de desarrollo. Es útil cuando se tiene una solución que consta de varios proyectos y se quiere mantener todo organizado en una estructura de solución 🚧🔧
        ```
        dotnet sln add API/
        ```
    ---

---

 - ### Referencias

    - Agrega una referencia al proyecto "Dominio" desde el proyecto "Aplicacion". Al hacer esto, el proyecto "Aplicacion" podrá acceder y utilizar las clases y funcionalidades proporcionadas por el proyecto "Dominio". Esto es útil cuando se tiene una estructura de capas en la que el proyecto de aplicación depende de lógica y modelos definidos en el proyecto de dominio y tambien agrega una referencia al proyecto "Persistencia" desde el proyecto "Aplicacion". Al hacer esto, el proyecto "Aplicacion" podrá acceder y utilizar las clases y funcionalidades proporcionadas por el proyecto "Persistencia". Esto es útil cuando se tiene una estructura de capas en la que el proyecto de aplicación necesita interactuar con la capa de persistencia, por ejemplo, para realizar operaciones de acceso a base de datos 🔗🔧
        ```
        cd Aplicacion/
        ```
        ```
        dotnet add reference ../Dominio/
        ```
        ```
        dotnet add reference ../Persistencia/
        ```
    
    ---
    - Agrega una referencia al proyecto "Aplicacion" desde el proyecto "API". Al hacer esto, el proyecto "API" podrá acceder y utilizar las clases y funcionalidades proporcionadas por el proyecto "Aplicacion". Esto es útil cuando se tiene una estructura de capas en la que el proyecto de la API necesita interactuar con la capa de aplicación para exponer funcionalidades a través de la interfaz de la API y tambien agrega una referencia al proyecto "Seguridad" desde el proyecto "API". Al hacer esto, el proyecto "API" podrá acceder y utilizar las clases y funcionalidades proporcionadas por el proyecto "Seguridad". Esto es útil cuando se tiene una estructura de capas en la que el proyecto de la API necesita interactuar con la capa de aplicación para exponer funcionalidades a través de la interfaz de la API 🔗🔧
        ```
        cd API/
        ```
        ```
        dotnet add reference ../Aplicacion/
        ```
    ---

    - Agrega una referencia al proyecto "Dominio" desde el proyecto "Persistencia". Al hacer esto, el proyecto "Persistencia" podrá acceder y utilizar las clases y funcionalidades proporcionadas por el proyecto "Dominio". Esto es útil cuando se tiene una estructura de capas en la que el proyecto de persistencia necesita acceder a los modelos y reglas de negocio definidos en el proyecto de dominio 🔗🔧
        ```
        cd Persistencia/
        ```
        ```
        dotnet add reference ../Dominio/
        ```
    ---


---
<img src="https://1.bp.blogspot.com/-epbYlUPl2-c/Xh6loHanlbI/AAAAAAAACpI/Ift8Ukv9AbQVIHl2aKTLMjr-LA25WN8lwCLcBGAsYHQ/s1600/ASP.NET%2BCore.jpg" alt="https://1.bp.blogspot.com/-epbYlUPl2-c/Xh6loHanlbI/AAAAAAAACpI/Ift8Ukv9AbQVIHl2aKTLMjr-LA25WN8lwCLcBGAsYHQ/s1600/ASP.NET%2BCore.jpg" style="width: 3000px;">

---


## Gestión de Datos

- ### Instalación de Paquetes

    - ### Dominio

        ---
        - La línea de comando dotnet add package Microsoft.EntityFrameworkCore --version 8.0.3 agrega el paquete "Microsoft.EntityFrameworkCore" a tu proyecto actual utilizando la versión 8.0.3 de Entity Framework Core. Este paquete es esencial para el desarrollo de aplicaciones .NET que requieren acceso a bases de datos relacionales. Entity Framework Core simplifica la interacción con bases de datos al permitirte trabajar con objetos de dominio en lugar de SQL directamente. Con características como el seguimiento de cambios, consultas LINQ y migraciones de base de datos, Entity Framework Core facilita el desarrollo y el mantenimiento de aplicaciones 📂🔧
            ```
           dotnet add package Microsoft.EntityFrameworkCore --version 8.0.3
            ```
            ---

        - Esta línea de comando agrega el paquete "MediatR.Extensions.Microsoft.DependencyInjection" a tu proyecto actual utilizando la versión 11.1.0. MediatR es una biblioteca que facilita la implementación del patrón Mediator en aplicaciones .NET. Al agregar este paquete, obtienes acceso a una serie de extensiones que integran MediatR con el contenedor de inyección de dependencias proporcionado por Microsoft.Extensions.DependencyInjection. Esto simplifica la configuración y la resolución de dependencias para tus controladores y manipuladores de MediatR, lo que facilita el desarrollo de aplicaciones escalables y mantenibles 📂🔧
            ```
            dotnet add package MediatR.Extensions.Microsoft.DependencyInjection --version 11.1.0
            ```
            ---

        - La línea de comando dotnet add package FluentValidation.AspNetCore --version 11.3.0 agrega el paquete "FluentValidation.AspNetCore" a tu proyecto actual utilizando la versión 11.3.0. Este paquete es una extensión de FluentValidation diseñada específicamente para integrarse con ASP.NET Core. FluentValidation es una biblioteca que simplifica la validación de modelos en aplicaciones .NET al permitirte definir reglas de validación de manera clara y legible utilizando un enfoque basado en fluidez 📂🔧
            ```
            dotnet add package FluentValidation.AspNetCore --version 11.3.0
            ```
            ---

        - La línea de comando dotnet add package itext7.pdfhtml --version 5.0.3 agrega el paquete "itext7.pdfhtml" a tu proyecto actual utilizando la versión 5.0.3. Este paquete proporciona funcionalidades para convertir documentos HTML a archivos PDF utilizando iText 7, una biblioteca de manipulación de documentos PDF en el entorno de desarrollo .NET. Al agregar este paquete a tu proyecto, podrás generar archivos PDF a partir de contenido HTML de manera eficiente y personalizable, lo que es útil para generar informes, documentos o páginas web como archivos PDF en tu aplicación 📂🔧
            ```
            dotnet add package itext7.pdfhtml --version 5.0.3
            ```
            ---


    - ### Persistencia 
        ---
        - La línea de comando dotnet add package Microsoft.EntityFrameworkCore --version 8.0.3 agrega el paquete "Microsoft.EntityFrameworkCore" a tu proyecto actual utilizando la versión 8.0.3 de Entity Framework Core. Este paquete es esencial para el desarrollo de aplicaciones .NET que requieren acceso a bases de datos relacionales. Entity Framework Core simplifica la interacción con bases de datos al permitirte trabajar con objetos de dominio en lugar de SQL directamente. Con características como el seguimiento de cambios, consultas LINQ y migraciones de base de datos, Entity Framework Core facilita el desarrollo y el mantenimiento de aplicaciones 📂🔧
            ```
            dotnet add package Microsoft.EntityFrameworkCore --version 8.0.3
            ```
            ---

        - La línea de comando dotnet add package Pomelo.EntityFrameworkCore.MySql --version 8.0.2 agrega el paquete "Pomelo.EntityFrameworkCore.MySql" a tu proyecto actual utilizando la versión 8.0.2. Este paquete proporciona soporte para MySQL en Entity Framework Core mediante la implementación de un proveedor de base de datos para MySQL. Al agregar esta versión específica, tu proyecto podrá utilizar Entity Framework Core para interactuar con bases de datos MySQL de manera eficiente y confiable. Esto incluye la capacidad de realizar operaciones de consulta, inserción, actualización y eliminación utilizando Entity Framework Core en un entorno que utiliza MySQL como sistema de gestión de bases de datos 📂🔧
            ```
            dotnet add package Pomelo.EntityFrameworkCore.MySql --version 8.0.2
            ```
            ---

        - La línea de comando dotnet add package Dapper --version 2.1.35 agrega el paquete "Dapper" a tu proyecto actual utilizando la versión 2.1.35. Dapper es una biblioteca de mapeo objeto-relacional (ORM) ligera y de alto rendimiento para .NET. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de Dapper para interactuar con bases de datos relacionales de una manera eficiente y simplificada. Dapper proporciona métodos de extensión simples pero potentes que te permiten ejecutar consultas SQL y mapear automáticamente los resultados a objetos .NET, lo que facilita el acceso y manipulación de datos en tu aplicación 📂🔧
            ```
            dotnet add package Dapper --version 2.1.35
            ```
            ---

    - ### API 
        ---
        - La línea de comando dotnet add package AspNetCoreRateLimit --version 5.0.0 agrega el paquete "AspNetCoreRateLimit" a tu proyecto actual utilizando la versión 5.0.0. Este paquete proporciona funcionalidades para limitar y controlar la tasa de solicitudes HTTP en aplicaciones ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de AspNetCoreRateLimit para implementar políticas de limitación de velocidad basadas en diferentes criterios, como la dirección IP, la ruta de la solicitud, el usuario, entre otros. Esto es útil para proteger tus servicios web contra ataques de denegación de servicio (DoS) y garantizar un rendimiento estable y equitativo para todos los clientes 📂🔧
            ```
            dotnet add package AspNetCoreRateLimit --version 5.0.0 
            ```
            ---

        - La línea de comando dotnet add package AutoMapper.Extensions.Microsoft.DependencyInjection --version 12.0.1 agrega el paquete "AutoMapper.Extensions.Microsoft.DependencyInjection" a tu proyecto actual utilizando la versión 12.0.1. Este paquete proporciona una integración fácil y conveniente de AutoMapper con el contenedor de inyección de dependencias de ASP.NET Core. AutoMapper es una biblioteca que simplifica la asignación de propiedades entre objetos en aplicaciones .NET. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de AutoMapper para configurar fácilmente la asignación de propiedades en tus servicios y controladores ASP.NET Core, lo que facilita el desarrollo de aplicaciones con menos código repetitivo y más legible 📂🔧
            ```
            dotnet add package AutoMapper.Extensions.Microsoft.DependencyInjection --version 12.0.1  
            ```
            ---

        - La línea de comando dotnet add package Microsoft.AspNetCore.Mvc.Versioning --version 5.1.0 agrega el paquete "Microsoft.AspNetCore.Mvc.Versioning" a tu proyecto actual utilizando la versión 5.1.0. Este paquete proporciona funcionalidades para la versión de API en aplicaciones ASP.NET Core MVC. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de versionado de API proporcionadas por Microsoft.AspNetCore.Mvc.Versioning para gestionar diferentes versiones de tus API, lo que permite una evolución controlada de tus servicios y una mejor experiencia para los usuarios y consumidores de la API 📂🔧
            ```
            dotnet add package Microsoft.AspNetCore.Mvc.Versioning --version 5.1.0 
            ```
            ---

        - La línea de comando dotnet add package Microsoft.AspNetCore.OpenApi --version 8.0.3 agregaría el paquete "Microsoft.AspNetCore.OpenApi" a tu proyecto actual utilizando la versión 8.0.3. Este paquete proporciona funcionalidades para generar documentación de API utilizando OpenAPI / Swagger en aplicaciones ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de generación de documentación de API proporcionadas por Microsoft.AspNetCore.OpenApi para exponer de manera clara y detallada los endpoints y modelos de datos de tus servicios web, lo que facilita la comprensión y la interacción con tu API 📂🔧
            ```
            dotnet add package Microsoft.AspNetCore.OpenApi --version 8.0.3
            ```
            ---

        - La línea de comando dotnet add package Microsoft.EntityFrameworkCore.Design --version 8.0.3 agrega el paquete "Microsoft.EntityFrameworkCore.Design" a tu proyecto actual utilizando la versión 8.0.3. Este paquete proporciona las herramientas de diseño necesarias para trabajar con Entity Framework Core en el entorno de desarrollo. Estas herramientas son esenciales para realizar tareas como generar migraciones de base de datos, actualizar la base de datos, y generar clases de contexto a partir de una base de datos existente 📂🔧
            ```
            dotnet add package Microsoft.EntityFrameworkCore.Design --version 8.0.3
            ```
           
            ---

        - La línea de comando dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer --version 8.0.3 agregaría el paquete "Microsoft.AspNetCore.Authentication.JwtBearer" a tu proyecto actual utilizando la versión 8.0.3. Este paquete proporciona soporte para la autenticación basada en tokens JWT (JSON Web Tokens) en aplicaciones ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de autenticación proporcionadas por Microsoft.AspNetCore.Authentication.JwtBearer para proteger tus endpoints de API mediante la verificación de tokens JWT, lo que garantiza un acceso seguro a tus recursos protegidos 📂🔧
            ```
            dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer --version 8.0.3
            ```
           
            ---

        - La línea de comando dotnet add package Swashbuckle.AspNetCore --version 6.5.0 agrega el paquete "Swashbuckle.AspNetCore" a tu proyecto actual utilizando la versión 6.5.0. Este paquete proporciona funcionalidades para generar documentación de API utilizando OpenAPI / Swagger en aplicaciones ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de generación de documentación de API proporcionadas por Swashbuckle.AspNetCore para exponer de manera clara y detallada los endpoints y modelos de datos de tus servicios web, lo que facilita la comprensión y la interacción con tu API 📂🔧
            ```
            dotnet add package Swashbuckle.AspNetCore --version 6.5.0  
            ```
            ---

        - La línea de comando dotnet add package Serilog.AspNetCore --version 8.0.1 agrega el paquete "Serilog.AspNetCore" a tu proyecto actual utilizando la versión 8.0.1. Este paquete proporciona integración de Serilog con ASP.NET Core, permitiéndote configurar y utilizar Serilog como tu proveedor de registros de forma sencilla en tu aplicación ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las capacidades de registro avanzadas proporcionadas por Serilog para gestionar y analizar registros de manera eficiente y flexible 📂🔧
            ```
            dotnet add package Serilog.AspNetCore --version 8.0.1
            ```
           
            ---

        - La línea de comando dotnet add package Swashbuckle.AspNetCore.Swagger --version 6.5.0 agrega el paquete "Swashbuckle.AspNetCore.Swagger" a tu proyecto actual utilizando la versión 6.5.0. Este paquete permite integrar Swagger con aplicaciones ASP.NET Core, facilitando la generación automática de documentación Swagger para tu API ASP.NET Core. Al agregar esta versión específica, tu proyecto puede aprovechar las últimas mejoras y características proporcionadas por Swashbuckle para generar y personalizar la documentación Swagger de tu API de manera eficiente 📂🔧
            ```
            dotnet add package Swashbuckle.AspNetCore.Swagger --version 6.5.0
            ```
           
            ---



<img src="https://cdn.icon-icons.com/icons2/2699/PNG/512/nuget_logo_icon_170908.png" alt="https://cdn.icon-icons.com/icons2/2699/PNG/512/nuget_logo_icon_170908.png" style="width: 3000px;">


- ### Migraciones    
    Se deben utilizar estos comandos para poder aplicar las migraciones y que los cambios se guarden en la base de datos ✈️🔧

    - ### Crear  
        - Este comando genera una migración inicial llamada "InitialCreate" utilizando Entity Framework Core. Las migraciones permiten mantener sincronizada la estructura de la base de datos con los cambios en el modelo de datos en proyectos .NET Core ✈️🔧
            ```
            dotnet ef migrations add InitialCreate --project ./Persistencia/ --startup-project ./API/ --output-dir ./Data/Migrations/  
            ```
            
        ---

    - ### Actualizar
        - Este comando aplica las migraciones pendientes en la base de datos, lo que implica actualizar la estructura de la base de datos para que coincida con el estado actual del modelo de datos en los proyectos .NET Core involucrados ✈️🔧
            ```
            dotnet ef database update --project ./Persistencia/ --startup-project ./API/  
            ```
            
        ---

- ### Visualización de posibles errores  
    Este comando se utiliza para construir (compilar) los proyectos en sus respectivos directorios, una ventaja que posee este comando es que nos permite ver que errores podemos tener a la hora de complilar 🏗️

    - Compila el proyecto ubicado en el directorio actual. Esto significa que el código fuente del proyecto se compilará en ensamblados ejecutables, bibliotecas u otros tipos de archivos de salida según la configuración del proyecto 🏗️
        ```
        dotnet build   
        ```

    ---
        

    **Ejemplos:**
    
    - Compila el proyecto ubicado en la carpeta "Persistencia". Esto significa que el código fuente del proyecto se compilará en ensamblados ejecutables, bibliotecas o archivos de salida según la configuración del proyecto 🏗️
        ```
        dotnet build ./Persistencia/
        ```
            
        ---
    - Compila el proyecto ubicado en la carpeta "API". Esto significa que el código fuente del proyecto se compilará en ensamblados ejecutables, bibliotecas o archivos de salida según la configuración del proyecto 🏗️
        ```
        dotnet build ./API/
        ```
            
     --- 
---

   <img src="https://dinahosting.com/blog/upload/2023/11/net-8.jpg" alt="img" style="width: 3000px;">

---


## Construcción del Código Base