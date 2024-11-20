# Examen-ETS-1-Trims

## Ejercicio 2

| **Actor**          | **Cliente**                                                                                           |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | Usuario que interactúa con el sistema para alquilar, reservar o devolver películas.                     |
| **Características**| Puede alquilar, reservar y devolver películas, además de proporcionar datos personales para registrarse.|
| **Relaciones**     | Interactúa con los casos de uso: Proporciona Datos Personales, Alquila Película, Devuelve Película, Reserva Película. |
| **Referencias**    | Es un usuario final del sistema VIDEOMAX que realiza operaciones relacionadas con películas.             |
| **Notas**          | El cliente debe estar registrado para acceder a todas las funcionalidades del sistema.                  |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Actor**          | **Administrador VIDEOMAX**                                                                            |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | Responsable de gestionar clientes, reservas, alquileres y el inventario del sistema.                    |
| **Características**| Tiene privilegios administrativos para registrar clientes, alquileres, reservas y películas.            |
| **Relaciones**     | Participa en los casos de uso: Registra a los Cliente, Registra Alquiler, Registra Reserva, Registra Película. |
| **Referencias**    | Rol interno del sistema encargado de la administración de operaciones y datos en VIDEOMAX.              |
| **Notas**          | Este actor tiene acceso completo al sistema para modificar información sensible.                        |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Actor**          | **Proveedor**                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | Encargado de suministrar películas y actualizar información relacionada con los proveedores.            |
| **Características**| Puede abastecer películas según la existencia y actualizar información sobre proveedores.               |
| **Relaciones**     | Participa en los casos de uso: Abastece Película, Abastece Película según Existencia, Actualiza Proveedor. |
| **Referencias**    | Relacionado con la cadena de suministro del inventario del sistema VIDEOMAX.                           |
| **Notas**          | El proveedor asegura que el inventario de películas esté al día.                                        |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Funcionalidad**  | **Proporciona Datos Personales**                                                                       |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | El cliente suministra información personal para registrarse en el sistema.                              |
| **Características**| Datos necesarios incluyen nombre, dirección, contacto, etc.                                            |
| **Relaciones**     | Caso de uso relacionado con el registro del cliente por parte del administrador.                        |
| **Referencias**    | Información almacenada en la base de datos del sistema VIDEOMAX.                                       |
| **Notas**          | Deben cumplirse normativas de protección de datos personales.                                           |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Funcionalidad**  | **Alquila Película**                                                                                  |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | El cliente selecciona y alquila una película, formalizando la operación.                                |
| **Características**| Incluye elección de película, confirmación y generación de un registro de alquiler.                    |
| **Relaciones**     | Incluye el caso de uso Seleccionar Película y se registra mediante el Administrador VIDEOMAX.           |
| **Referencias**    | Relacionado con las operaciones de registro de alquiler en el sistema.                                 |
| **Notas**          | El alquiler puede tener restricciones según la disponibilidad.                                         |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Funcionalidad**  | **Devuelve Película**                                                                                  |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | El cliente devuelve una película previamente alquilada.                                                |
| **Características**| Requiere validación de la fecha de devolución y el estado de la película.                              |
| **Relaciones**     | Se relaciona con el caso de uso Alquila Película.                                                      |
| **Referencias**    | Actualiza el estado del inventario y las estadísticas de alquiler.                                     |
| **Notas**          | Puede haber penalizaciones por devoluciones tardías.                                                  |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Relación**       | **Alquila Película incluye Seleccionar Película**                                                      |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | Seleccionar una película es una acción necesaria para completar un alquiler.                           |
| **Características**| Parte del proceso de alquiler; permite al cliente elegir entre las opciones disponibles.               |
| **Relaciones**     | Origen: Alquila Película, Destino: Seleccionar Película.                                               |
| **Referencias**    | Relacionado con la disponibilidad de películas en el inventario.                                       |
| **Notas**          | La película seleccionada debe estar disponible para el alquiler.                                      |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Relación**       | **Reserva Película incluye Seleccionar Película**                                                      |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | Seleccionar una película es una acción necesaria para completar una reserva.                           |
| **Características**| Parte del proceso de reserva; permite al cliente elegir entre las opciones disponibles.                |
| **Relaciones**     | Origen: Reserva Película, Destino: Seleccionar Película.                                               |
| **Referencias**    | Relacionado con el registro de reservas en el sistema.                                                |
| **Notas**          | La reserva está sujeta a la disponibilidad futura de la película.                                      |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |

---

| **Relación**       | **Abastece Película según Existencia extiende Abastece Película**                                       |
|--------------------|-------------------------------------------------------------------------------------------------------|
| **Descripción**    | La lógica de existencia extiende el caso general de suministro de películas.                           |
| **Características**| Proceso automatizado o manual para evaluar y actualizar inventario según la demanda.                   |
| **Relaciones**     | Origen: Abastece Película según Existencia, Destino: Abastece Película.                                 |
| **Referencias**    | Dependiente de los registros de inventario del sistema VIDEOMAX.                                       |
| **Notas**          | Asegura que no se generen excesos ni faltantes en el inventario.                                       |
| **Autor**          | Diego Febles Seoane                                                                                    |
| **Fecha**          | 20/11/2024                                                                                            |
