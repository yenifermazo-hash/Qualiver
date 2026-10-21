# 02 — Regla de oro: SIEMPRE la base de datos principal

## Por qué existe esta regla
Ya nos pasó: se trabajó sobre una base de datos que no era la principal y los cambios **no se reflejaron** donde se necesitaban. Se perdió tiempo y hubo que rehacer.

Separar desarrollo y producción es una buena práctica en otros lugares, **pero en Qualiver no la usamos en estos proyectos**. Aquí se trabaja **siempre en la principal**. Sin excepciones.

## La regla
- ✅ Todo cambio (datos, columnas, tablas, funciones, vistas, políticas) se hace en la base **principal** del proyecto.
- ❌ Nunca se trabaja en tablas o bases de desarrollo, pruebas o copias.

## Nombres sospechosos (si aparecen, NO se usan y se avisa)
`dev`, `development`, `desarrollo`, `test`, `testing`, `prueba`, `pruebas`, `staging`, `stage`, `sandbox`, `copia`, `copy`, `backup`, `bk`, `old`, `viejo`, `temp`, `tmp`, `demo`, `v2` (si no es la principal)

Si el nombre de la tabla/base tiene cualquiera de estas palabras → Claude **para** y pregunta:
> "Encontré `<nombre>`, que parece de pruebas/copia. La base principal registrada es `<principal>`. ¿Sigo en la principal?"

## Qué debe quedar escrito en el CLAUDE.md
```markdown
## Base de datos principal  ⚠️ OBLIGATORIO
- Tipo: Supabase / Google Sheets / Otra: ______
- Nombre: ______
- ID / URL / Project ref: ______
- Tablas principales:
  - `tabla_1` → para qué sirve
  - `tabla_2` → para qué sirve
- Tablas/bases PROHIBIDAS (no tocar): ______ (o "ninguna conocida")
- Confirmado por: ______  Fecha: ______
```

## Cómo se verifica según el tipo de base

### Supabase
- Confirmar el **Project ref / URL** (ej. `https://xxxxx.supabase.co`) contra el `CLAUDE.md`.
- Revisar que las variables de conexión del proyecto (`.env`) apunten a ese mismo proyecto.
- Si hay más de un proyecto de Supabase conectado → preguntar cuál es el principal antes de cualquier cosa.

### Google Sheets
- Confirmar el **ID del archivo** (lo que va entre `/d/` y `/edit` en el enlace) contra el `CLAUDE.md`.
- Confirmar el **nombre exacto de la hoja (pestaña)**.
- Si existe una "copia de…" del mismo archivo → no se usa.
- Si la app (AppSheet, N8N, Looker) lee de ese Sheet, confirmar que apunta al mismo ID.

### Otra
- Anotar en el `CLAUDE.md` cómo identificar la principal (nombre, URL, ID) y verificar contra eso.

## Antes de CADA cambio a datos o estructura
Claude dice, en una línea:
> "Voy a `<acción>` en `<tabla>` de `<base principal>`. ¿Confirmas?"

Y espera el sí.

## Si algo no cuadra
- La base que está usando no coincide con la del `CLAUDE.md` → **parar y avisar**.
- No hay base registrada en el `CLAUDE.md` → **parar y preguntar**.
- Nunca "suponer" cuál es la principal.
