# 05 — Instructivo de uso

Al terminar el proyecto (o cuando lo pidan), Claude construye el instructivo para el usuario final.
Se entrega en **dos formatos**:

1. **Markdown** dentro del proyecto: `docs/INSTRUCTIVO.md` (plantilla: `plantillas/INSTRUCTIVO.md`)
2. **Word + PDF con formato Qualiver**, para enviar al cliente

## De dónde sale la información
- `docs/PRD.md` → roles, funcionalidades, proceso
- `CLAUDE.md` → proceso del cliente y decisiones
- Lo que realmente se construyó (no lo que se pensó al principio)

Si algo del PRD no se construyó, **no va** en el instructivo.

## Cómo se escribe
- Lenguaje sencillo, para alguien que nunca ha usado la app.
- Pasos numerados, una acción por paso.
- Separado por **rol** (qué hace el gerente, qué hace el comercial, etc.).
- Cada pantalla o función: para qué sirve → cómo se usa → qué pasa después.
- Donde haga falta una captura de pantalla, dejar la marca: `[Captura: descripción de lo que debe verse]`.
- Al final: preguntas frecuentes y a quién contactar si algo falla.

## Estructura
1. Portada (nombre de la app, cliente, fecha, versión)
2. ¿Para qué sirve esta app?
3. Cómo entrar
4. Recorrido general (menú y pantallas)
5. Instrucciones por rol
6. Proceso completo paso a paso (con estados)
7. Reportes y notificaciones
8. Preguntas frecuentes
9. Soporte (contacto Qualiver)

## Word + PDF con formato Qualiver
- Si está disponible la skill **`qualiver-manual-usuario`**, usarla: ya tiene el branding de Qualiver.
- Si no está disponible: generar el `.docx` a partir de `docs/INSTRUCTIVO.md` con los colores y logo de Qualiver, y exportarlo a PDF.
- Guardar ambos en `docs/` con el nombre: `Instructivo_<NombreApp>_<AAAA-MM-DD>.docx` / `.pdf`

## Antes de entregar
Claude muestra el instructivo y pregunta: *"¿Lo reviso con algún cambio o lo dejo así?"*
