# 03 — Preguntas de proceso (antes de construir)

Antes de construir, Claude debe entender **cuál es el proceso** del cliente.
Se pregunta de a **3 o 4 preguntas por vez**, no todas de golpe. Las respuestas se anotan en el `CLAUDE.md`, sección "Proceso del cliente".

Si una respuesta no está clara, se vuelve a preguntar. No se supone nada.

## Bloque 1 — El cliente y el problema
1. ¿Quién es el cliente y a qué se dedica?
2. ¿Qué problema quiere resolver con esta solución?
3. ¿Cómo lo hace hoy? (Excel, papel, WhatsApp, otra app…)
4. ¿Qué es lo que más le duele del proceso actual?

## Bloque 2 — El proceso paso a paso
5. ¿Cuál es el proceso de principio a fin? (qué pasa primero, qué después)
6. ¿Qué estados tiene un registro? (ej. Pendiente → En proceso → Terminado)
7. ¿Quién hace cada paso? (roles: gerente, comercial, operario…)
8. ¿Qué pasa cuando algo sale mal o se devuelve? (excepciones)

## Bloque 3 — Los datos
9. ¿Cuál es la base de datos **principal**? (tipo, nombre, enlace/ID) → ver guía 02
10. ¿Qué tablas existen hoy y qué guarda cada una?
11. ¿Hay tablas de pruebas, copias o desarrollo que debamos **evitar**?
12. ¿Hay datos que no se pueden tocar o borrar?

## Bloque 4 — Lo que se espera
13. ¿Qué debe poder hacer cada usuario en la solución?
14. ¿Qué reportes, tableros o notificaciones necesita? (Looker, WhatsApp, correo…)
15. ¿Con qué otras herramientas se conecta? (AppSheet, N8N, Looker Studio, otras)
16. ¿Cómo sabremos que el proyecto quedó bien? (qué tiene que funcionar sí o sí)
17. ¿Hay fecha de entrega?

## Al terminar
Claude muestra un **resumen del proceso** en lenguaje sencillo:
- Pasos del proceso en orden
- Roles y qué hace cada uno
- Base principal y tablas
- Qué se espera de la solución

Y pregunta: *"¿Este resumen está bien o corrijo algo?"*
Solo con el sí se pasa al PRD.
