# Análisis QA y Testing de Software 

Este repositorio contiene simulaciones y casos prácticos de QA Testing aplicados a diferentes entornos web. Se documentan las funcionalidades probadas, el reporte de bugs encontrados, los pasos para su reproducción y la clasificación de su impacto.

> **Nota:** Todos los casos incluyen documentación de respaldo (capturas de pantalla) y fueron gestionados inicialmente mediante matrices de prueba en Excel.

---

## Caso 1: Software de Gestión de Pedidos 
**Contexto:** Optimización y arreglo de procesos para un sistema de catering y venta de productos artesanales.

**Funcionalidades probadas:**
* Verificación de stock.
* Seguridad de la pasarela de compras.
* Sistema de pedidos vía web.
* Verificador y registro de clientes.
* Modificación de recetas en base de datos.
* Interfaz de contacto con el servicio de delivery.

<img width="1555" height="640" alt="image" src="https://github.com/user-attachments/assets/8777e93d-f184-439e-b12a-8883ec082f52" />


**Reporte de Bug**
* **Bug ID:** `0123d`
* **Título:** Fallo crítico en el formulario de registro de nuevos clientes.
* **Pasos para reproducir:**
  1. Navegar a la página de registro.
  2. Completar todos los campos obligatorios del formulario.
  3. Hacer clic en el botón “Registrar”.
* **Resultado Esperado:** El sistema crea la cuenta y redirige al panel de usuario.
* **Resultado Real:** Ausencia de respuesta en la interfaz del cliente; la consola arroja un error `400 Bad Request`.
* **Severidad:** Crítica | **Prioridad:** Alta


---

## Caso 2: App Web Búsqueda de Vuelos - Búsqueda de Vuelos (App Web- Despegar)
**Contexto:** Pruebas de integración en el motor de búsqueda principal.

**Funciones probadas:**
* Seleccionador de aeropuerto de origen y destino.
* Seleccionador de fechas (ida y vuelta).
* Selector de cantidad de pasajeros.
* Motor central de búsqueda de vuelos.

<img width="1385" height="341" alt="image" src="https://github.com/user-attachments/assets/5a58753a-eeb0-46af-b15f-5689e7be248b" />


**Reporte de Bug**
* **Bug ID:** `A005`
* **Título:** Caída del motor de búsqueda de vuelos.
* **Pasos para reproducir:**
  1. Completar los campos de origen, destino, fechas y pasajeros con datos válidos.
  2. Presionar el botón “Buscar”.
* **Resultado Esperado:** Despliegue de la lista de vuelos disponibles según los filtros.
* **Resultado Real:** Redirección a una página en blanco; error de autenticación con proxy `407 Proxy Authentication Required`.
* **Severidad:** Crítica | **Prioridad:** Alta


---

## Caso 3: App Web de Video (Simulación YouTube)
**Contexto:** Pruebas de usabilidad e interacción de la interfaz de usuario.

**Funciones probadas:**
* Reproducción y pausa de videos.
* Control de volumen.
* Sistema de suscripciones.
* Alternancia a modo pantalla completa.
* Ajuste de velocidad de reproducción.

  <img width="1518" height="414" alt="image" src="https://github.com/user-attachments/assets/38624f91-8f8b-479f-9fb6-c45966a796a9" />


**Reporte de Bug**
* **Bug ID:** `b129`
* **Título:** Bloqueo de estado en el botón de desuscripción.
* **Pasos para reproducir:**
  1. Suscribirse a un canal presionando el botón “Suscribirse”.
  2. Intentar revertir la acción presionando el mismo botón (ahora etiquetado como “Desuscribirse”).
* **Resultado Esperado:** El usuario deja de estar suscrito al canal y el botón vuelve a su estado inicial.
* **Resultado Real:** La interfaz (UI) del botón se inmoviliza y la petición de desuscripción no se envía al servidor.
* **Severidad:** Mayor | **Prioridad:** Alta


---

## Caso 4: Cliente de Correo (Simulación Gmail)
**Contexto:** Pruebas de validación de campos y formato de texto (Rich Text).

**Funciones probadas:**
* Validación de campos “Para” y “Asunto”.
* Ejecución del botón “Enviar”.
* Restricciones de caracteres máximos.
* Herramientas de cambio de formato de fuente.
* Función de adjuntar archivos.
* Inserción y parseo de hipervínculos (URLs).

<img width="1527" height="516" alt="image" src="https://github.com/user-attachments/assets/a895c95c-76aa-4d2a-a047-d0db79fc1659" />

  

**Reporte de Bugs**

**Bug ID:** `me239`
* **Título:** Fallo en el parseo automático de hipervínculos funcionales.
* **Pasos para reproducir:**
  1. Copiar tres URLs distintas (ej. YouTube, Instagram, Facebook).
  2. Pegar los enlaces en el cuerpo del correo manteniendo el formato original.
* **Resultado Esperado:** El sistema debe reconocer la estructura y convertir el texto en hipervínculos funcionales automáticamente.
* **Resultado Real:** Las URLs se insertan y mantienen en formato de texto plano inactivo.
* **Severidad:** Menor | **Prioridad:** Media


**Bug ID:** `me236`
* **Título:** Ausencia de validación en el límite máximo de caracteres del cuerpo del mensaje.
* **Pasos para reproducir:**
  1. Escribir una cadena de más de 100 caracteres alfabéticos en el cuadro de mensaje.
  2. Repetir la prueba inyectando números y caracteres especiales (`. , - _`) superando la barrera de los 100 caracteres.
* **Resultado Esperado:** El sistema debe bloquear la entrada de texto al alcanzar el límite establecido e informar al usuario.
* **Resultado Real:** No existe validación de límite; el campo permite entrada infinita de texto.
* **Severidad:** Moderada | **Prioridad:** Media
