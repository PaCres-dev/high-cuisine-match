# Origen de estas skills

Copiadas desde [mattpocock/skills](https://github.com/mattpocock/skills) — las
skills de Matt Pocock para ingeniería real. Licencia MIT (ver `LICENSE`).

| | |
|---|---|
| Repo origen | `https://github.com/mattpocock/skills` |
| Commit | `3cca18b368ae95cdbdebbff572ccafa662551015` |
| Versión | 1.2.3 |
| Copiado el | 2026-09-05 |

Se copiaron las **25 skills publicadas** (las que lista
`.claude-plugin/plugin.json` del repo origen): las categorías `engineering` y
`productivity`. Se omitieron `in-progress`, `misc` y `deprecated`.

Dos ajustes respecto al origen:

1. Las carpetas de categoría (`engineering/`, `productivity/`) se aplanaron,
   porque Claude Code busca las skills de proyecto en
   `.claude/skills/<nombre>/SKILL.md`. No hubo colisiones de nombre.
2. Se omitieron los directorios `agents/` (metadatos `openai.yaml` del
   instalador skills.sh para agentes que no son Claude Code).

El contenido de cada `SKILL.md` y sus archivos de apoyo está intacto.

## Actualizar

Estas skills son **copias que ahora te pertenecen**: nada se actualiza solo, y
si las editas los cambios son tuyos. Para traer los cambios de upstream:

```bash
npx skills@latest update
```

O manualmente, revisando el diff antes de pisar ediciones locales:

```bash
git clone --depth 1 https://github.com/mattpocock/skills.git /tmp/mp-skills
diff -ru .claude/skills/tdd /tmp/mp-skills/skills/engineering/tdd
```
