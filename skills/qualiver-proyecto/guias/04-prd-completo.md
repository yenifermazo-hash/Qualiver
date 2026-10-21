# 04 — PRD completo (documento de requerimientos)

El PRD dice **qué debe hacer la solución, para quién y cómo**. Es el mapa del proyecto.
Se arma con `plantillas/PRD.md` y se guarda en el proyecto como `docs/PRD.md`.

**Regla: no se empieza a construir hasta que este checklist esté completo y el PRD aprobado.**

## Checklist — todo debe estar en ✅

### Contexto
- [ ] Nombre del proyecto y del cliente
- [ ] Problema que se resuelve (en 2-3 frases)
- [ ] Cómo se hace hoy

### Usuarios
- [ ] Lista de roles
- [ ] Qué puede ver y hacer cada rol

### Proceso
- [ ] Pasos del proceso en orden
- [ ] Estados de los registros y cómo se pasa de uno a otro
- [ ] Excepciones (devoluciones, cancelaciones, errores)

### Datos
- [ ] **Base de datos principal** (tipo, nombre, ID/URL) — igual a la del `CLAUDE.md`
- [ ] Tablas con sus columnas principales y para qué sirven
- [ ] Relaciones entre tablas
- [ ] Tablas prohibidas (dev/pruebas/copias) o "ninguna"

### Funcionalidades
- [ ] Lista de funcionalidades, cada una con:
  - Qué hace
  - Quién la usa
  - Cómo se sabe que funciona (criterio de aceptación)
- [ ] Prioridad de cada una (imprescindible / deseable)

### Integraciones y salidas
- [ ] Herramientas conectadas (AppSheet, N8N, Looker Studio, Supabase, Sheets, WhatsApp…)
- [ ] Reportes, tableros, notificaciones o documentos que genera

### Cierre
- [ ] Qué queda **fuera** del alcance
- [ ] Fecha de entrega (si hay)
- [ ] Preguntas pendientes (deben quedar en cero para empezar)
- [ ] Aprobado por: ______ Fecha: ______

## Cómo lo revisa Claude
1. Llena el PRD con lo que salió de las preguntas de proceso.
2. Recorre el checklist y marca qué falta.
3. Pregunta **solo** lo que falta.
4. Muestra el PRD terminado y pide aprobación.
5. Si después cambia algo del alcance → se actualiza el PRD primero y luego se construye.
