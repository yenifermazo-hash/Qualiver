# 06 — Actualizar el CLAUDE.md y manejar el contexto

## Qué es el "contexto"
Es todo lo que Claude tiene en la cabeza en la conversación actual: lo que le dijimos, lo que leyó, lo que hizo.
Tiene un límite. Cuando se llena:
- Claude se pone más lento y empieza a olvidar cosas del principio.
- Al resumirse la conversación, se pueden perder detalles.

Lo único que **no se pierde nunca** es lo que está escrito en el `CLAUDE.md`, porque se vuelve a leer siempre.
Por eso: **lo importante se escribe en el `CLAUDE.md` antes de que el contexto se llene.**

## Cómo ver qué tan lleno está
Escribir `/context`. Muestra el porcentaje usado.

## Cuándo actualizar el CLAUDE.md

| Momento | Qué hacer |
|---|---|
| Contexto al **50%** | Actualizar `CLAUDE.md` → luego `/compact` |
| Contexto al **80%** | **Obligatorio:** actualizar `CLAUDE.md` → luego `/clear` (conversación nueva) |
| Se toma una decisión importante | Anotarla en "Decisiones y cambios" en ese momento |
| Cambia la base principal o una tabla | Actualizar "Base de datos principal" en ese momento |
| Al terminar la sesión del día | Actualizar "Estado actual" y "Próximos pasos" |
| Antes de pasarle el proyecto a otro compañero | Revisar que el `CLAUDE.md` esté al día |

Claude debe **avisar** cuando note que la conversación ya va larga:
> "La conversación va avanzada. ¿Actualizo el CLAUDE.md antes de seguir?"

## Qué se actualiza (y qué no)
✅ Sí va en el `CLAUDE.md`:
- Base de datos principal y tablas
- Proceso del cliente (resumen)
- Decisiones tomadas y por qué
- Estado actual: qué está hecho, qué falta
- Próximos pasos
- Errores que ya pasaron y cómo se resolvieron

❌ No va en el `CLAUDE.md`:
- Contraseñas, llaves de API o tokens (eso va en `.env`, que **no** se sube a GitHub)
- Conversaciones completas o código largo copiado
- Cosas temporales que no sirven mañana

Mantenerlo **corto y claro**. Si una sección crece mucho, resumirla.

## Frases para pedirle a Claude
- *"Actualiza el CLAUDE.md con lo que hicimos y lo que falta."*
- *"Revisa el /context y dime si toca actualizar el CLAUDE.md."*
- *"Antes de compactar, guarda en el CLAUDE.md las decisiones de hoy."*

## Orden correcto al compactar o limpiar
1. Actualizar el `CLAUDE.md`.
2. Revisar que quedó bien (mostrarlo).
3. Recién ahí `/compact` o `/clear`.
4. Después de `/clear`: pedir *"Lee el CLAUDE.md y dime en qué quedamos"*.
