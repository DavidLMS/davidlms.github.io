summary: Cómo evaluar RAs y CEs usando el libro de calificaciones de Moodle
id: moodle-calificaciones-ra-ce
categories: Moodle
tags: moodle
status: Published
authors: [David Romero](https://davidlms.com)
feedback link: https://github.com/DavidLMS/davidlms.github.io/issues/new?title=Error+en+gu%C3%ADa+Wireguard+en+Ubuntu+Server

# Calificando Resultados de Aprendizaje y Criterios de Evaluación en Moodle
## Introducción
Duration: 1

A raíz del artículo [Evaluar por Resultados de Aprendizaje y Criterios de Evaluación sin morir en el intento](https://davidlms.com/evaluar-por-resultados-de-aprendizaje-y-criterios-de-evaluación-sin-morir-en-el-intento/) en el [blog](https://davidlms.com), he recibido bastantes correos con preguntas sobre cómo llevar un registro de esas calificaciones sin preocuparnos durante el curso por el cálculo.

En esta guía, os contaré cómo lo hago yo.

Evidentemente, pueden usarse muchas aplicaciones para ello. Desde una simple hoja de cálculo a una herramienta como Additio o iDoceo. Pero a mí me gusta hacerlo directamente en la plataforma Moodle donde están alojados los cursos virtuales de las distintas materias. Esto me da una serie de ventajas:
- Puedo decidir que el alumnado vea la evolución de sus calificaciones en tiempo real, escribiendo la calificación una sola vez.
- Está todo centralizado en un mismo sitio: aula virtual, materiales didácticos, entrega de tareas y calificaciones.
- Al ser un recurso proporcionado por la administración educativa, no tengo que preocuparme de la Ley de Protección de Datos.
- En Andalucía podemos exportar las calificaciones desde Moodle al sistema de gestión Séneca (el registro oficial de la Junta de Andalucía para los datos del alumnado y sus calificaciones).

Voy a indicar paso por paso qué es lo que configuro, partiendo de las siguientes premisas:
- Las actividades de aprendizaje son de entrega obligatoria, pero solamente tienen una valoración cualitativa que no influye en las calificaciones.
- La calificación de cada Resultado de Aprendizaje es una media ponderada de los Criterios de Evaluación en función de los diferentes pesos que haya establecido para cada uno: Básico (4), Intermedio (2) o Avanzado (1).
- La calificación de cada Criterio de Evaluación será la máxima de todos los instrumentos en los que se haya evaluado. Normalmente evalúo cada criterio con un solo instrumento, si tengo dos es porque el segundo es una recuperación.
- La calificación de cada Evaluación es una media ponderada de los Resultados de Aprendizaje que haya trabajado durante la misma.
- La calificación Final es una media ponderada de todos los Resultados de Aprendizaje.

![Diagrama propuesto para la práctica](img/diagrama.png)

Crearemos un túnel VPN de comunicación segura entre cada uno de los clientes y el servidor.

**Nota importante 1**: Para seguir esta guía necesitas que el servidor que vayas a utilizar tenga una IP pública. Como es poco habitual que esto ocurra en un entorno de prácticas, tienes la opción de configurar un reenvío de puerto.
Si lo haces en tu casa, configura en tu router que el puerto 51820 sea redirigido al puerto 51820 de la IP local de tu servidor.
Si lo haces en un aula, pide a tu instructor que lo haga cuando quieras hacer la prueba de conexión.
Si no fuera posible ninguna de las opciones anteriores, quizás puedas alquilar un servidor público para hacer la prueba. Por ejemplo, servicios en la nube como AWS y Azure ofrecen cuentas con créditos gratuitos para estudiantes.

**Nota importante 2**: Durante la guía, todos los parámetros que haya que sustituir se mostrarán entre corchetes. Por ejemplo, si la IP de tu servidor es 192.168.1.100 y en el comando aparece [IP_SERVIDOR]:
```
ping [IP_SERVIDOR]
```
Tendrás que sustituirlo por tu parámetro sin incluir los corchetes. Por ejemplo:
```
ping 192.168.1.100
```
<!-- ------------------------ -->
## Cómo funciona el libro de calificaciones de Moodle
Duration: 2

En el libro de calificaciones de Moodle hay dos conceptos básicos. Podemos crear ítems o categorías:
- Los ítems son calificaciones directas de un instrumento. Son calificaciones que escribe el docente.
- Las categorías son calificaciones calculadas en base a ítems u otras categorías. Son calificaciones que calcula Moodle y no tiene que escribir el docente manualmente.

A lo largo de esta guía, configuraré el siguiente árbol de categorías e ítems:

- Primera Evaluación (categoría)
  - Unidad 1 (categoría)
    - Criterio 1a (categoría)
      - Instrumento para evaluar el criterio 1a (ítem)
    - Criterio 1b (categoría)
      - Instrumento para evaluar el criterio 1b (ítem)
    - Criterio 1c (categoría)
      - Instrumento para evaluar el criterio 1c (ítem)
    ...
    - Criterio Xx
      - Instrumento para evaluar el criterio Xx (ítem)
  - Unidad 2
  ...
  - Unidad X
- Segunda Evaluación (categoría)
  - Unidad X (categoría)
    - Criterio Xx (categoría)
      - Instrumento para evaluar el criterio Xx (ítem)
    ...
  ...
- Tercera Evaluación (categoría)
  - Unidad X (categoría)
    - Criterio Xx (categoría)
      - Instrumento para evaluar el criterio Xx (ítem)
    ...
  ...
- Resultados de Aprendizaje (categoría)
  - RA 1 (categoría)
  - RA 2 (categoría)
  - RA 3 (categoría)
  ...
  - RA X (categoría)

<!-- ------------------------ -->
## Configurar las escalas para actividades
Duration: 25

<!-- ------------------------ -->
## Configurar las categorías
Duration: 25

<!-- ------------------------ -->
## Configurar los instrumentos
Duration: 25

### Tarea de Moodle

### Tarea de Google

<!-- ------------------------ -->
## Bonus: Creación y asignación de rúbricas
Duration: 25

### Tarea de Moodle

### Tarea de Google

<!-- ------------------------ -->
## Créditos
Duration: 1

El autor de este Codelab es [David Romero](https://davidlms.com/). Eres libre de compartirlo y modificarlo siguiendo la licencia [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/deed.es).