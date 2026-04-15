# 🔐 Laboratorio #2 – Implementación del Login en Laravel

> **Curso:** Desarrollo Web VII | **Unidad I:** Modelo Vista Controlador (MVC)  
> **Universidad Tecnológica de Panamá** – Facultad de Ingeniería de Sistemas Computacionales  
> **Instructor:** Ing. Irina Fong

---

## 📋 Descripción

Este repositorio documenta la implementación del módulo de autenticación (Login) en Laravel,
siguiendo la arquitectura Modelo-Vista-Controlador (MVC). Se evidencia el proceso de
configuración, los comandos utilizados, la estructura del proyecto y los resultados obtenidos.

---

## 🎯 Objetivos

- Comprender la importancia de la documentación en proyectos de desarrollo de software.
- Consolidar el aprendizaje de la arquitectura MVC en Laravel.
- Evidenciar el proceso de configuración e implementación del módulo de login en Laravel.
- Identificar las dificultades encontradas durante el laboratorio y las soluciones aplicadas.
- Generar un repositorio académico organizado como referencia para futuras prácticas.

---

## ⚙️ Requisitos Previos

| Tecnología | Versión / Detalle |
|---|---|
| 🐘 PHP | 8.0 o superior |
| 🎼 Composer | Última versión estable |
| 🛠️ Laravel Installer | `laravel new` o `composer create-project` |
| 🌐 Servidor local | XAMPP / WampServer / Laragon |
| 🖥️ Servidor web | Apache o Nginx |
| 🗄️ Base de datos | MySQL / MariaDB |
| 💻 Editor de código | Visual Studio Code (recomendado) |
| 📦 NPM | [Versión utilizada o "No requerido"] |
| 🪟 Sistema Operativo | [Windows 10/11 u otro] |

---

## 🚀 Instalación y Configuración

### 1. Clonar o crear el proyecto

```bash
# Laravel Installer
laravel new LaboratorioLaravel
```

### 2. Instalar dependencias

```bash
composer install
```

### 3. Configurar el archivo `.env`

```bash
cp .env.example .env
php artisan key:generate
```

Editar las siguientes variables en `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nombre_base_datos
DB_USERNAME=root
DB_PASSWORD=
```

### 4. Paquete de autenticación

**Laravel Breeze:**

```bash
composer require laravel/breeze --dev
php artisan breeze:install
npm install && npm run dev
```

---

## 🗂️ Estructura MVC del Proyecto

Laravel organiza el código siguiendo el patrón **Modelo – Vista – Controlador**:

| Carpeta | Rol en MVC | Descripción |
|---|---|---|
| `app/Models/` | **Modelo** | Clases que representan las tablas de la base de datos (ej. `User.php`) |
| `app/Http/Controllers/` | **Controlador** | Lógica de negocio; reciben peticiones y devuelven respuestas |
| `resources/views/` | **Vista** | Plantillas Blade que renderizan el HTML mostrado al usuario |
| `routes/web.php` | **Rutas** | Define las URLs y las asocia a controladores o vistas |
| `database/migrations/` | **Migraciones** | Definen la estructura de las tablas de la base de datos |

---

## 🗄️ Base de Datos

### Configuración en `.env`

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=[nombre_db]
DB_USERNAME=root
DB_PASSWORD=
```

### Comandos de migración utilizados

```bash
# Crear las tablas en la base de datos
php artisan migrate

# Si necesitas reiniciar todas las migraciones
php artisan migrate:fresh

# Ver el estado de las migraciones
php artisan migrate:status
```

### Tablas generadas

- `users` – Almacena los usuarios registrados (email, password, timestamps).
- `password_reset_tokens` – Gestiona los tokens para restablecimiento de contraseña.
- `sessions` – [Si aplica] Manejo de sesiones en base de datos.

> 📁 El respaldo de la base de datos se encuentra en: [`/database/backup/backup.sql`](./database/backup/backup.sql)

---

## ⚠️ Dificultades y Soluciones

| # | Problema encontrado | Solución aplicada |
|---|---|---|
| 1 | [Ej. Error en migraciones por versión de MySQL] | [Ej. Cambiar el motor en `AppServiceProvider`] |
| 2 | [Ej. `.env` no reconocido] | [Ej. Ejecutar `php artisan config:clear`] |
| 3 | [Ej. NPM no compilaba assets] | [Ej. Reinstalar con `npm install` y correr `npm run dev`] |

---

## 📚 Referencias

1. Laravel Documentation – Authentication: https://laravel.com/docs/11.x/authentication
2. Laravel Breeze – Starter Kit: https://laravel.com/docs/11.x/starter-kits#laravel-breeze
3. PHP - https://www.php.net/
---

## 📅 Fecha de Ejecución del Laboratorio

**Fecha de realización:** [08/04/2026]  

---

## 👤 Desarrollado por

---

> Este laboratorio ha sido desarrollado por el estudiante de la **Universidad Tecnológica de Panamá**:
>
> | Campo | Detalle |
> |---|---|
> | **Nombre** | [Roniel Quintero] |
> | **Correo** | [roniel.quintero@utp.ac.pa] |
> | **Curso** | Desarrollo de Software VII (DSVII) |
> | **Instructor** | Ing. Irina Fong |
