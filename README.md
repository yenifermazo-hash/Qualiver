# qualiver-claude-code

Forma de trabajo del equipo Qualiver con **Claude Code**, empaquetada como una skill.

Sirve para que todos los proyectos (tipo el portal de la Fundación) se armen igual:
1. Preguntar primero cuál es el proceso del cliente.
2. Trabajar **SIEMPRE en la base de datos principal** — nunca en tablas de development, pruebas o copias.
3. Tener un **PRD completo** antes de construir.
4. Construir el **instructivo de uso** al final (Markdown + Word/PDF Qualiver).
5. Mantener el **CLAUDE.md** al día y cuidar el contexto.

---

## Qué hay en este repositorio

```
qualiver-claude-code/
├── README.md                                ← este archivo
└── skills/
    └── qualiver-proyecto/
        ├── SKILL.md                         ← el flujo que sigue Claude
        ├── guias/
        │   ├── 01-como-funciona-claude-code.md
        │   ├── 02-regla-base-principal.md
        │   ├── 03-preguntas-de-proceso.md
        │   ├── 04-prd-completo.md
        │   ├── 05-instructivo-de-uso.md
        │   └── 06-claude-md-y-contexto.md
        └── plantillas/
            ├── CLAUDE.md
            ├── PRD.md
            └── INSTRUCTIVO.md
```

---

## Cómo instalarla (una sola vez por computador)

**1. Clonar el repositorio**
```bash
git clone https://github.com/<usuario>/qualiver-claude-code.git
```

**2. Copiar la skill a tu carpeta de Claude** (queda disponible en todos tus proyectos)

Mac / Linux:
```bash
mkdir -p ~/.claude/skills
cp -r qualiver-claude-code/skills/qualiver-proyecto ~/.claude/skills/
```

Windows (PowerShell):
```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills"
Copy-Item -Recurse -Force "qualiver-claude-code\skills\qualiver-proyecto" "$HOME\.claude\skills\"
```

**3. Comprobar**
Abrir Claude Code en cualquier carpeta (`claude`) y escribir:
```
¿Tienes disponible la skill qualiver-proyecto?
```

## Cómo actualizarla cuando alguien la mejore

Mac / Linux:
```bash
cd qualiver-claude-code
git pull
cp -r skills/qualiver-proyecto ~/.claude/skills/
```

Windows (PowerShell):
```powershell
cd qualiver-claude-code
git pull
Copy-Item -Recurse -Force "skills\qualiver-proyecto" "$HOME\.claude\skills\"
```

---

## Cómo usarla

**Proyecto nuevo** — abrir Claude Code en la carpeta del proyecto y escribir:
```
Arranquemos este proyecto con la skill qualiver-proyecto.
```

**Proyecto existente:**
```
Lee el CLAUDE.md y dime en qué quedamos.
```

**Cuando la conversación va larga:**
```
Revisa el /context y actualiza el CLAUDE.md si toca.
```

**Al terminar:**
```
Construye el instructivo de uso con la skill qualiver-proyecto.
```

---

## La regla que no se negocia

> En Qualiver trabajamos **siempre en la base de datos / tabla principal**.
> Nunca en development, pruebas ni copias. Así los cambios se reflejan donde se necesitan.

## Cómo proponer mejoras
Si encuentras algo que falta o que se puede mejorar, edita los archivos, haz commit y avisa al equipo para que hagan `git pull`.
