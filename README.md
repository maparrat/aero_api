# MISW4403 - Diseño y construcción de APIs  
## Parcial práctico
# Miguel Armando Parra 201814632
### Instrucciones

1. Cree un nuevo proyecto de Nest.js.  
2. Abra el proyecto en el editor de su preferencia.  
3. Suba el proyecto a un repositorio de GitHub en su cuenta personal.  
4. Haga commit y push en su repositorio bifurcado periódicamente.  

---

## Punto 1. Persistencia (6%)

Esta aplicación tiene el propósito de crear un sistema de consulta de cobertura de las aerolíneas.

1. Cree la entidad **Aerolinea** en el módulo correspondiente. Una aerolínea tiene:  
   - nombre  
   - descripción  
   - fecha de fundación  
   - página web  

2. Cree la entidad **Aeropuerto** en el módulo correspondiente. Un aeropuerto tiene:  
   - nombre  
   - código  
   - país  
   - ciudad  

3. Incluya la **asociación entre Aerolínea y Aeropuerto**:  
   - Un aeropuerto cuenta con múltiples aerolíneas.  
   - Una aerolínea tiene cobertura en distintos aeropuertos.  

---

## Punto 2. Lógica (43%)

1. Defina la lógica de **Aerolinea**, debe incluir los métodos:  
   - `findAll`  
   - `findOne`  
   - `create`  
   - `update`  
   - `delete`  

   > En `create` y `update`, valide que la fecha de fundación sea en el pasado.

2. Defina la lógica de **Aeropuerto**, debe incluir los métodos:  
   - `findAll`  
   - `findOne`  
   - `create`  
   - `update`  
   - `delete`  

   > En `create` y `update`, valide que el código del aeropuerto tenga **únicamente tres caracteres**.

3. Defina la lógica de la **asociación**, debe incluir los siguientes métodos:
   - `addAirportToAirline`: Asociar un aeropuerto a una aerolínea.  
   - `findAirportsFromAirline`: Obtener los aeropuertos que cubre una aerolínea.  
   - `findAirportFromAirline`: Obtener un aeropuerto que cubre una aerolínea.  
   - `updateAirportsFromAirline`: Actualizar los aeropuertos que cubre una aerolínea.  
   - `deleteAirportFromAirline`: Eliminar los aeropuertos que cubre una aerolínea.

4. Implemente las **pruebas unitarias** para:  
   - Lógica de Aerolínea  
   - Lógica de Aeropuerto  
   - Lógica de la Asociación  

---

## Punto 3. API (24%)

1. Cree el **controlador de Aerolinea**, con la ruta `/airlines` y defina los endpoints:  
   - `findAll`  
   - `findOne`  
   - `create`  
   - `update`  
   - `delete`  

2. Cree el **controlador de Aeropuerto**, con la ruta `/airports` y defina los endpoints:  
   - `findAll`  
   - `findOne`  
   - `create`  
   - `update`  
   - `delete`  

3. Cree el **controlador de la asociación Aerolínea-Aeropuerto**, con rutas como:  
   - `/airlines/1/airports/4`  

   Implemente los siguientes endpoints:
   - `addAirportToAirline`  
   - `findAirportsFromAirline`  
   - `findAirportFromAirline`  
   - `updateAirportsFromAirline`  
   - `deleteAirportFromAirline`  

---

## Punto 4. Pruebas de Postman (27%)

Defina **3 colecciones** de Postman con las siguientes pruebas para las entidades y para la asociación:

| Método | Aerolíneas                           | Aeropuertos                           | Aerolíneas-Aeropuertos                                        |
|--------|--------------------------------------|---------------------------------------|---------------------------------------------------------------|
| POST   | Crear una aerolínea válida.          | Crear un aeropuerto válido.           | Asociar un aeropuerto a una aerolínea.                        |
| POST   | Crear una aerolínea inválida.        | Crear un aeropuerto inválido.         | Asociar un aeropuerto que no existe a una aerolínea.          |
| GET    | Obtener todas las aerolíneas.        | Obtener todos los aeropuertos.        | Obtener todos los aeropuertos que cubre una aerolínea.        |
| GET    | Obtener una aerolínea por ID.        | Obtener un aeropuerto por ID.         | Obtener un aeropuerto asociado a una aerolínea.               |
| GET    | Obtener una aerolínea por ID inválido| Obtener un aeropuerto por ID inválido | Obtener un aeropuerto que no esté asociado a una aerolínea.   |
| PUT    | Actualizar una aerolínea.            | Actualizar un aeropuerto.             | Actualizar los aeropuertos asociados a una aerolínea.         |
| PUT    | Actualizar con ID inválido.          | Actualizar con ID inválido.           | Actualizar con un aeropuerto inexistente.                     |
| DELETE | Eliminar una aerolínea por ID.       | Eliminar un aeropuerto por ID.        | Eliminar un aeropuerto asociado a una aerolínea.              |
| DELETE | Eliminar con ID inválido.            | Eliminar con ID inválido.             | Eliminar un aeropuerto no asociado a una aerolínea.           |

---

## Entregable

- Dentro del proyecto Nest.js cree una carpeta llamada `collections` y exporte ahí las colecciones de Postman.  
- Suba todos los cambios a su repositorio.  
- Haga un **release** con el tag `v1.0.0` y el nombre `parcial-practico`.  
- Suba el archivo `.zip` del release como respuesta en la actividad de Coursera.  
- **Después del plazo de entrega no realice ninguna modificación al repositorio.**  
  > Cualquier cambio, por pequeño que sea, anula automáticamente el parcial.
