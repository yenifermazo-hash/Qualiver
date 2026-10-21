# CLAUDE.md — <Nombre del proyecto>

> Este archivo es la memoria del proyecto. Claude Code lo lee siempre al abrir.
> Se trabaja con la skill **qualiver-proyecto**. Mantenerlo corto y al día.

## ⚠️ REGLA DE ORO
Trabajar **SIEMPRE** en la base de datos principal de abajo.
**NUNCA** usar tablas o bases de desarrollo, pruebas, copias, staging, "_dev", "_test", "_copia", "_old".
Antes de cada cambio a datos o estructura: decir qué se va a cambiar y en qué tabla, y esperar confirmación.
Si la base en uso no coincide con la de abajo → parar y avisar.

## Base de datos principal  ⚠️ OBLIGATORIO
- Tipo: <Supabase / Google Sheets / Otra: ___>
- Nombre: <___>
- ID / URL / Project ref: <___>
- Tablas principales:
  - `<tabla>` → <para qué sirve>
- Tablas/bases PROHIBIDAS (no tocar): <___ o "ninguna conocida">
- Confirmado por: <___>  Fecha: <AAAA-MM-DD>

## Proyecto
- Cliente: <___>
- Qué resuelve: <2-3 frases>
- Equipo Qualiver: <nombres>
- PRD: `docs/PRD.md`
- Instructivo: `docs/INSTRUCTIVO.md`

## Proceso del cliente (resumen)
1. <paso>
2. <paso>
- Estados: <Pendiente → En proceso → Terminado>
- Roles: <rol → qué hace>

## Herramientas y conexiones
- <AppSheet / N8N / Looker Studio / Supabase / Google Sheets / otra> → <para qué>
- Credenciales: en `.env` (NUNCA en este archivo ni en GitHub)

## Forma de trabajo
- Paso a paso, confirmando cada etapa.
- Lenguaje claro, sin tecnicismos.
- Hacer solo lo que se pide; nada de cambios extra.
- Revisar `/context`: al 50% actualizar este archivo y `/compact`; al 80% actualizar y `/clear`.

## Decisiones y cambios
- <AAAA-MM-DD> — <decisión> — <por qué>

## Errores que ya pasaron (no repetir)
- <AAAA-MM-DD> — <qué pasó> — <cómo se resolvió>

## Estado actual
- Hecho: <___>
- En curso: <___>

## Próximos pasos
- <___>
