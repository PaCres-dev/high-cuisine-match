# Configuración de Claude Code

Este directorio contiene la configuración de Claude Code de
`high-cuisine-match`, versionada para que todo el equipo trabaje igual.

## Skills

Las skills de [Matt Pocock](https://github.com/mattpocock/skills) están
**copiadas directamente en el repo**, en `.claude/skills/`. No hay plugin ni
marketplace de por medio: son archivos normales que se clonan con el repo,
funcionan sin instalar nada y se pueden editar para adaptarlos al proyecto.

Ver [`skills/SOURCE.md`](./skills/SOURCE.md) para el commit exacto de origen y
cómo traer actualizaciones de upstream.

### Cómo se usan

Claude Code carga estas skills automáticamente al abrir una sesión en el repo.
Al ser skills de proyecto (no de plugin) **no llevan prefijo**: se invocan
directamente, por ejemplo `/tdd` o `/code-review`. Claude también las usa por su
cuenta cuando la tarea encaja con su `description`.

Para comprobar que están cargadas: `/help` → pestaña **Custom commands**.

### Qué hay disponible

**Ingeniería** (18)

| Skill | Para qué |
|---|---|
| `ask-matt` | Router: te dice qué skill o flujo encaja con tu situación |
| `code-review` | Revisar los cambios desde un punto fijo (commit, rama, merge-base) |
| `codebase-design` | Vocabulario común para diseñar módulos profundos |
| `diagnosing-bugs` | Bucle de diagnóstico para bugs difíciles y regresiones de rendimiento |
| `domain-modeling` | Construir y afinar el modelo de dominio del proyecto |
| `grill-with-docs` | Interrogatorio de un plan que además produce ADRs y glosario |
| `implement` | Implementar a partir de una spec o de un set de tickets |
| `improve-codebase-architecture` | Buscar oportunidades de mejora y reportarlas en HTML |
| `prototype` | Prototipo descartable para responder una pregunta de diseño |
| `research` | Investigar contra fuentes primarias y dejar las conclusiones en Markdown |
| `resolving-merge-conflicts` | Resolver un merge o rebase con conflictos en curso |
| `setup-matt-pocock-skills` | Configurar el repo para estas skills (issue tracker, etiquetas de triage) |
| `tdd` | Ciclo red-green-refactor con tests que valen la pena mantener |
| `to-spec` | Convertir la conversación en una spec y publicarla en el issue tracker |
| `to-tickets` | Partir un plan o spec en tickets tipo bala trazadora |
| `triage` | Mover issues y PRs externos por una máquina de estados de triage |
| `wayfinder` | Planificar trabajo que no cabe en una sola sesión, como mapa compartido |
| `wizard` | Generar un asistente bash para los pasos que solo puede hacer una persona |


**Productividad** (7)

| Skill | Para qué |
|---|---|
| `grill-me` | Que te interroguen sobre tu plan hasta que se sostenga |
| `grilling` | El motor de interrogatorio que usa `grill-me` |
| `handoff` | Comprimir la conversación en un documento para que otro agente siga |
| `teach` | Aprender una habilidad o concepto dentro de este workspace |
| `to-questionnaire` | Convertir una decisión que no puedes cerrar en un cuestionario para otro |
| `wait-what` | "Ese mensaje no llegó": pedir que se replantee |
| `writing-for-agents` | Escribir skills, AGENTS.md o CLAUDE.md que un agente sí siga |


### Primer paso recomendado

```
/setup-matt-pocock-skills
```

Adapta las skills a este repositorio (stack, convenciones, comandos de test).
Como las skills son archivos del repo, esos ajustes se commitean y le sirven a
todo el equipo.

## Notas

- **No instales además el plugin** `mattpocock-skills` ni ejecutes
  `npx skills@latest add mattpocock/skills`: tendrías cada skill duplicada.
- `grill-me`, `code-review` y `research` pueden coincidir en nombre con skills
  que ya trae tu Claude Code. Si pasa, las de proyecto conviven con las
  integradas; el menú de `/help` muestra ambas.
- `.claude/settings.local.json` es para ajustes personales y está en
  `.gitignore`.

## Referencias

- [Agent Skills](https://code.claude.com/docs/en/skills)
- [Settings reference](https://code.claude.com/docs/en/settings-reference)
