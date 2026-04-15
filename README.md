# Laboratorio: Autenticación en Laravel

## 1. Prerrequisitos (Entorno de Desarrollo)

Para la ejecución de este laboratorio se requiere el siguiente ecosistema de desarrollo:

*   **PHP:** Versión 8.0 o superior ![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=flat&logo=php&logoColor=white)
*   **Composer:** Última versión estable ![Composer](https://img.shields.io/badge/composer-%23000000.svg?style=flat&logo=composer&logoColor=white)
*   **Laravel:** Creado con `composer create-project laravel/laravel` ![Laravel](https://img.shields.io/badge/laravel-%23FF2D20.svg?style=flat&logo=laravel&logoColor=white)
*   **Entorno Local:** Paquete de servidor web local (WampServer) ![WampServer](https://img.shields.io/badge/wampserver-%23FF0000.svg?style=flat&logo=wamp&logoColor=white)
*   **Servidor Web:** Apache
*   **Base de Datos:** MySQL / MariaDB ![MySQL](https://img.shields.io/badge/mysql-%2300000f.svg?style=flat&logo=mysql&logoColor=white)
*   **Editor de Código:** Visual Studio Code ![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=flat&logo=visual-studio-code&logoColor=white)
*   **Gestor de Paquetes Node:** NPM ![NPM](https://img.shields.io/badge/npm-%23CB3837.svg?style=flat&logo=npm&logoColor=white)
*   **Sistema Operativo:** Windows

---

## 2. Introducción y Objetivo del Laboratorio

**Objetivo:** Implementar un sistema de autenticación utilizando Laravel, configurando la base de datos, migraciones y dependencias necesarias para gestionar el registro y acceso de usuarios.

**Arquitectura MVC en Laravel:**

La arquitectura Modelo-Vista-Controlador (MVC) organiza el código en tres capas principales:

*   **Carpetas Principales:**
    *   `app/Models/`: Contiene los Modelos, que interactúan de forma directa con la base de datos utilizando el ORM Eloquent.
    *   `app/Http/Controllers/`: Contiene los Controladores, encargados de recibir las peticiones, procesar la lógica y retornar una respuesta a la vista.
    *   `resources/views/`: Almacena las Vistas (archivos `.blade.php`), que son las interfaces de usuario que muestran la información en el navegador.
    *   `routes/`: Define las rutas de la aplicación web, conectando URLs específicas con sus respectivos controladores y métodos.

---

## 3. Instalación de Dependencias y Configuración

Secuencia de comandos utilizados para la instalación del proyecto y dependencias de autenticación:

```bash

# Instalación del paquete Laravel UI (Autenticación)
composer require laravel/ui

# Instalación del proyecto Laravel
composer create-project laravel/laravel LoginLaravel || laravel new LoginLaravel

# Generación de scaffolding de autenticación con Bootstrap
php artisan ui bootstrap --auth

# Instalación de dependencias de Node.js y compilación de assets
npm install && npm run dev

# Correr el panel de Laravel, es recomendado de iniciarlo en otra pestaña de terminal.
php artisan serve 
```

---

## 4. Base de Datos, Entorno y Migraciones

**Configuración del entorno (.env):**
Se configuraron las credenciales de la base de datos MySQL en el archivo `.env` del proyecto:
(Puede llamar a la base de datos "laravel")

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=<nombre_de_la_base_de_datos> 
DB_USERNAME=root
DB_PASSWORD=
```

**Migraciones:**
Laravel utiliza migraciones para controlar las versiones de la base de datos. Para construir las tablas requeridas por el sistema de autenticación, se ejecutó el siguiente comando:

```bash
php artisan migrate
```

**Problemas con la base de datos no creándose porque ya existe o tiene una configuración incorrecta:**
# Esto borra toda la base de datos.
```bash
php artisan db:wipe
```
# y después corre 
```bash
php artisan migrate
```
---

## 5. Resultado del Laboratorio

![Resultado de Autenticación]()
*(Nota: Inserte aquí la imagen con el resultado visible de la pantalla de Login/Registro)*

---

## 6. Dificultades y Soluciones

*   **Desafío:** (Ejemplo: Archivo .env no configurado correctamente al inicio).
*   **Solución:** (Ejemplo: Revisión y ajuste de los puertos y credenciales de MySQL en el sistema WampServer).

*   **Desafío:** (Ejemplo: Problemas con la compilación de activos usando Vite/NPM).
*   **Solución:** (Ejemplo: Asegurarse de tener Node actualizado y ejecutar npm run dev adecuadamente).

---

## 7. Referencias

*   Documentación Oficial de Laravel: https://laravel.com/docs
*   Material de apoyo del curso.

---

## 8. Fecha de Ejecución del Laboratorio

**Fecha:** 8 de abril de 2026

---

## 9. Autoría

Este laboratorio ha sido desarrollado por:

*   **Nombre:** Andre Reboulet
*   **Correo:** andre.reboulet@utp.ac.pa
*   **Curso:** Desarrollo de Software VII en el grupo 1GS131
*   **Instructor del Laboratorio:** Irina Fong
