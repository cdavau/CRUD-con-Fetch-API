# 🛒 Laboratorio: CRUD con Fetch API + PHP OOP + MySQL

**Asignatura:** Desarrollo de Software VII  
**Grupo:** 1GS132 
**Instructor:** Ing. Irina Fong  
**Estudiante:** Carlos Abadia  
**Semestre:** I Semestre 2026

---

## Introducción

En este laboratorio se desarrolló una aplicación web dinámica bajo la arquitectura cliente-servidor, integrando peticiones asíncronas con **Fetch API** y un backend robusto en **PHP orientado a objetos** con **MySQL**. Se implementó un CRUD completo para la gestión de productos, con validaciones tanto en el cliente como en el servidor, y alertas amigables con **SweetAlert2**.

---

## Tecnologías utilizadas

- HTML5 + CSS3
- Bootstrap 5
- JavaScript (Fetch API)
- SweetAlert2
- PHP 7+ (POO)
- MySQL (PDO)
- Apache (WAMP)

---

## Base de datos

```sql
CREATE DATABASE IF NOT EXISTS productosdb;
USE productosdb;

CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    codigo VARCHAR(20) NOT NULL,
    producto VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    cantidad INT NOT NULL
);
```
<img width="1601" height="507" alt="image" src="https://github.com/user-attachments/assets/ae5404bd-2d5d-4437-9696-37b6beae970f" />

---

## Funcionalidades

### 1. Registrar producto
Formulario con validaciones. SweetAlert muestra éxito o errores.

<img width="1260" height="828" alt="image" src="https://github.com/user-attachments/assets/ceecbb59-78a0-4bfe-bc66-8fee7bbf01e2" />

---

### 2. Listar productos
La tabla se actualiza automáticamente al cargar la página y tras cada operación.

<img width="1171" height="830" alt="image" src="https://github.com/user-attachments/assets/00318212-8049-4f6b-b836-55ed2d413c83" />

---

### 3. Buscar producto
Se ingresa el código en el formulario y haz clic en **Buscar**. Los datos se cargan automáticamente.

<img width="1312" height="852" alt="image" src="https://github.com/user-attachments/assets/428763c0-0f19-4d6c-840b-9c338a3e4486" />


---

### 4. Editar producto
Al hacer clic en **Editar** en la tabla o buscar por código, el formulario se llena con los datos del producto.

<img width="1198" height="866" alt="image" src="https://github.com/user-attachments/assets/a72981e9-2629-43a9-af3d-557ab2569e04" />

---

### 5. Actualizar producto
Modifica los datos y haz clic en **Actualizar**. SweetAlert confirma el éxito.

<img width="1306" height="863" alt="image" src="https://github.com/user-attachments/assets/0468a7b7-6009-4d97-a4cc-6135a24cf86d" />

---

### 6. ❌ Validación de errores
Si un campo está vacío o tiene datos inválidos, SweetAlert muestra los errores.

<img width="1113" height="637" alt="image" src="https://github.com/user-attachments/assets/6eb3f99b-6762-4364-a82e-d90097dee8d9" />


---

## Cómo funciona

### Switch en PHP (`registrar.php`)
Centraliza todas las operaciones CRUD según la acción recibida por POST:
```php
switch ($accion) {
    case 'Guardar':   // insertar
    case 'Modificar': // actualizar
    case 'Buscar':    // consultar por código
    case 'Listar':    // traer todos
}
```

### Switch en JavaScript (`script.js`)
Procesa la respuesta JSON del servidor:
```javascript
switch (data.accion) {
    case 'guardar':   // mostrar éxito y limpiar form
    case 'editar':    // mostrar éxito y recargar tabla
}
```

### Respuestas JSON
El servidor siempre responde con:
```json
{
    "success": true,
    "message": "Producto guardado correctamente",
    "accion": "guardar"
}
```

---

## Conclusión

A través de este laboratorio se logró implementar una aplicación web dinámica integrando Fetch API con PHP orientado a objetos y MySQL. Se aplicaron buenas prácticas como el uso de PDO para prevenir inyecciones SQL, validaciones en cliente y servidor, respuestas JSON estructuradas y alertas amigables con SweetAlert2. La arquitectura con clases y un controlador central con switch facilita el mantenimiento y escalabilidad del proyecto.

---


