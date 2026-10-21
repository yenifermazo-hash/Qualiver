---
name: qualiver-proyecto
description: Flujo de trabajo de Qualiver para proyectos con Claude Code. Usar al arrancar un proyecto nuevo, al retomar uno existente, al tocar cualquier base de datos o tabla (Supabase, Google Sheets u otra), al armar el PRD, al construir el instructivo de uso o cuando la conversación ya va larga y hay que actualizar el CLAUDE.md.
---

# Proyectos Qualiver con Claude Code

Esta skill es la forma de trabajo del equipo. Se sigue en orden y **no se salta ninguna etapa**.
Trabajamos paso a paso: al terminar cada etapa, Claude muestra lo que hizo y **espera confirmación** antes de seguir.
Lenguaje claro, sin tecnicismos innecesarios. Claude hace solo lo que se le pide: nada de trabajo extra ni cambios que nadie pidió.

---

## REGLA DE ORO: siempre la base de datos PRINCIPAL

> En Qualiver trabajamos **siempre** sobre la base de datos / tabla **principal** del proyecto.
> **Nunca** sobre tablas de development, pruebas, copias, "staging", "_dev", "_test", "_copia", "_old" o similares.

Antes de leer, crear, modificar o borrar CUALQUIER dato o estructura:

1. Revisar en el `CLAUDE.md` del proyecto la sección **"Base de datos principal"**.
2. Si esa sección no existe o está vacía → **parar y preguntar** (ver `guias/02-regla-base-principal.md`). No se adivina.
3. Confirmar en voz alta antes de cada cambio: *"Voy a modificar `<tabla>` en `<base principal>`. ¿Confirmas?"*
4. Si aparece cualquier tabla o base con nombre de desarrollo/prueba/copia → **no se usa** y se avisa.

Detalle completo: `guias/02-regla-base-principal.md`.

---

## Flujo de trabajo (en orden)

### Etapa 0 — ¿Proyecto nuevo o existente?
- Si **no** existe `CLAUDE.md` en la raíz del proyecto → es nuevo. Copiar `plantillas/CLAUDE.md` a la raíz y seguir con la Etapa 1.
- Si **sí** existe → leerlo completo antes de hacer cualquier cosa. Revisar que la sección "Base de datos principal" esté llena. Si falta algo, completarlo preguntando.

### Etapa 1 — Preguntas de proceso
Antes de escribir una sola línea, entender el proceso del cliente.
Hacer las preguntas de `guias/03-preguntas-de-proceso.md` (de a pocas, no todas de golpe).
Anotar las respuestas en el `CLAUDE.md` (sección "Proceso del cliente").
➡️ Mostrar resumen y esperar confirmación.

### Etapa 2 — Base de datos principal
Preguntar y dejar escrito en el `CLAUDE.md`:
- Tipo (Supabase, Google Sheets u otra)
- Nombre exacto / ID / URL de la base principal
- Tablas principales y para qué sirve cada una
- Tablas o bases **prohibidas** (dev, pruebas, copias) si existen
➡️ Esperar confirmación.

### Etapa 3 — PRD completo
Armar el PRD con la plantilla `plantillas/PRD.md` y el checklist de `guias/04-prd-completo.md`.
Guardarlo como `docs/PRD.md` en el proyecto.
**No se empieza a construir hasta que el checklist del PRD esté 100% completo y aprobado.**
➡️ Esperar aprobación del PRD.

### Etapa 4 — Construcción
- Trabajar por partes pequeñas, una a la vez, siguiendo el PRD.
- Antes de cada cambio a datos o estructura: aplicar la Regla de Oro.
- Al terminar cada parte: decir qué se hizo, en qué tabla y cómo probarlo. Esperar confirmación.
- Actualizar el `CLAUDE.md` (sección "Decisiones y cambios") cuando se tome una decisión importante.

### Etapa 5 — Instructivo de uso
Al terminar (o cuando lo pidan), construir el instructivo siguiendo `guias/05-instructivo-de-uso.md`.
Se entrega en los dos formatos: Markdown dentro del proyecto **y** Word + PDF con formato Qualiver.

### Siempre — Cuidar el contexto y el CLAUDE.md
Seguir `guias/06-claude-md-y-contexto.md`:
- Revisar el uso de contexto con `/context`.
- Al pasar el **50%** → actualizar el `CLAUDE.md` y luego `/compact`.
- Al llegar al **80%** → es obligatorio: actualizar `CLAUDE.md`, y abrir conversación nueva con `/clear`.
- Al cerrar cada sesión de trabajo → actualizar el `CLAUDE.md`.

---

## Archivos de esta skill

| Archivo | Para qué |
|---|---|
| `guias/01-como-funciona-claude-code.md` | Qué es Claude Code y cómo trabajamos con él |
| `guias/02-regla-base-principal.md` | La regla de la base principal, sin excepciones |
| `guias/03-preguntas-de-proceso.md` | Preguntas obligatorias antes de construir |
| `guias/04-prd-completo.md` | Checklist para que el PRD no quede incompleto |
| `guias/05-instructivo-de-uso.md` | Cómo construir el instructivo de uso |
| `guias/06-claude-md-y-contexto.md` | Cuándo y cómo actualizar el CLAUDE.md y manejar el contexto |
| `plantillas/CLAUDE.md` | Plantilla base para cada proyecto |
| `plantillas/PRD.md` | Plantilla del PRD |
| `plantillas/INSTRUCTIVO.md` | Plantilla del instructivo en Markdown |
