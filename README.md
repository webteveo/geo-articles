# geo-articles

Skill `geo-article`: artículos de blog para sitios de servicios locales (UY y AR), escritos para que los citen las IAs y rankeen en Google, sin tics de texto generado.

## Instalar (para usarla en cualquier lado)

- **claude.ai / app de escritorio / celular**: descargá `geo-article.zip` de este repo y subilo en Configuración → Capacidades → Skills → Subir skill. Queda en tu cuenta para todos los chats.
- **Claude Code en cualquier carpeta**:
  ```bash
  git clone https://github.com/webteveo/geo-articles.git ~/geo-articles
  mkdir -p ~/.claude/skills && cp -r ~/geo-articles/.claude/skills/geo-article ~/.claude/skills/
  ```
- **Dentro de este repo** no hay que instalar nada: Claude Code la carga sola.

## Usar

1. Pedí "escribí un artículo sobre <keyword> para <sitio>" (o `/geo-article` en Claude Code).
2. Pasale la ficha del sitio: adjuntá el `.yaml`, pegala, o tenela en `sites/<sitio>.yaml` si trabajás en este repo. Formato: `sites/_ejemplo.yaml`. Si no tenés ficha, la skill la arma con vos.
3. Te hace hasta 3 preguntas de experiencia, investiga, arma un brief y escribe el borrador con los `[DATO FALTANTE]` marcados.
4. Linter: `python3 .claude/skills/geo-article/scripts/check_ai_tells.py <articulo>.md` (`--final` antes de publicar). Tests: `python3 -m pytest .claude/skills/geo-article/scripts -q`.
5. Ejemplo completo en `articulos/_ejemplo/` (negocio ficticio, no publicar).

Si cambiás la skill, regenerá el zip: `cd .claude/skills && zip -r ../../geo-article.zip geo-article -x '*/__pycache__/*'`.
