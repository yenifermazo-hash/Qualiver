# 01 — Cómo funciona Claude Code (y cómo lo usamos en Qualiver)

## ¿Qué es?
Claude Code es Claude trabajando directamente dentro de la carpeta del proyecto. No solo responde: **lee los archivos, los modifica, ejecuta comandos y se conecta a herramientas** (por ejemplo Supabase) para hacer el trabajo con nosotros.

Por eso hay que darle reglas claras: si no sabe cuál es la base principal, puede trabajar en la equivocada. Esta skill existe para que eso no pase.

## Las 3 piezas que hay que entender

### 1. El `CLAUDE.md` — la memoria del proyecto
- Es un archivo de texto en la raíz del proyecto.
- Claude Code lo lee **automáticamente** cada vez que se abre en esa carpeta.
- Ahí va todo lo que Claude debe saber siempre: qué es el proyecto, cuál es la base principal, el proceso del cliente, decisiones tomadas.
- Si algo no está en el `CLAUDE.md`, Claude no lo va a recordar en la próxima conversación.
- Se crea con la plantilla `plantillas/CLAUDE.md` (o con el comando `/init` y luego se completa con la plantilla).

### 2. Las skills — las formas de trabajar
- Una skill es una carpeta con instrucciones (un archivo `SKILL.md`) que Claude sigue cuando la tarea lo necesita.
- Esta carpeta (`qualiver-proyecto`) es una skill.
- Dónde se instalan:
  - **Para todos tus proyectos:** `~/.claude/skills/qualiver-proyecto/` (en tu usuario)
  - **Solo para un proyecto:** `.claude/skills/qualiver-proyecto/` (dentro de la carpeta del proyecto)

### 3. Los settings — los permisos y reglas
Hay 3 niveles, todos se llaman `settings.json`:

| Nivel | Dónde está | Se comparte por Git | Para qué |
|---|---|---|---|
| Usuario | `~/.claude/settings.json` | No | Preferencias tuyas en todos los proyectos |
| Proyecto | `.claude/settings.json` | **Sí** | Reglas del equipo para ese proyecto |
| Local | `.claude/settings.local.json` | No | Ajustes tuyos solo en ese proyecto |

Si chocan, gana el más específico: **Local > Proyecto > Usuario**.

## Comandos que más vamos a usar

| Comando | Qué hace |
|---|---|
| `claude` | Abre Claude Code en la carpeta donde estés |
| `/init` | Crea un `CLAUDE.md` inicial revisando el proyecto |
| `/memory` | Abre el `CLAUDE.md` para editarlo |
| `/context` | Muestra qué tan llena está la conversación (contexto) |
| `/compact` | Resume la conversación para liberar espacio sin perder el hilo |
| `/clear` | Empieza una conversación nueva desde cero (el `CLAUDE.md` se vuelve a leer) |
| `Esc` | Detiene a Claude si va por mal camino |

## Cómo es trabajar con Claude Code el día a día
1. Abrir la terminal en la carpeta del proyecto y escribir `claude`.
2. Si es proyecto nuevo: pedir *"Arranquemos el proyecto con la skill qualiver-proyecto"*.
3. Si es existente: Claude lee el `CLAUDE.md` solo. Pedirle *"Revisa el CLAUDE.md y dime en qué quedamos"*.
4. Pedir las cosas de a una, revisar lo que hizo y confirmar antes de seguir.
5. Vigilar el contexto con `/context` y actualizar el `CLAUDE.md` (ver guía 06).
6. Al terminar el día: *"Actualiza el CLAUDE.md con lo que hicimos hoy"*.

## Errores comunes que evitamos
- ❌ Trabajar sin `CLAUDE.md` → Claude no sabe nada del proyecto.
- ❌ No dejar escrita la base principal → puede usar una de pruebas.
- ❌ Dejar que la conversación se llene sin actualizar el `CLAUDE.md` → se pierde lo decidido.
- ❌ Pedir muchas cosas a la vez → difícil de revisar.

Documentación oficial: https://docs.claude.com/en/docs/claude-code/overview
