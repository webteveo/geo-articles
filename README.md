# geo-articles

Fábrica de artículos de blog para los sitios de servicios locales de Webteveo (UY y AR), escritos para que los citen las IAs y rankeen en Google, sin tics de texto generado.

1. Creá la ficha del sitio: copiá `sites/_ejemplo.yaml` a `sites/<sitio>.yaml` y completala con datos reales (precios con fecha, casos, errores comunes, autor, páginas).
2. En Claude Code, dentro de este repo: `/geo-article` o "escribí un artículo para <sitio> sobre <keyword>".
3. La skill te hace hasta 3 preguntas de experiencia, investiga la SERP, arma un brief y escribe el borrador.
4. Salida: `articulos/<sitio>/<slug>.md` (+ `<slug>.brief.md`). Al final del archivo hay un comentario con los `[DATO FALTANTE]` a completar.
5. Linter: `python3 .claude/skills/geo-article/scripts/check_ai_tells.py articulos/<sitio>/<slug>.md` (sale con código 1 si hay alertas altas).
6. Antes de publicar: completá los faltantes y corré el linter con `--final`.
7. Frases prohibidas editables en `.claude/skills/geo-article/scripts/frases_prohibidas.txt`.
8. Tests del linter: `python3 -m pytest .claude/skills/geo-article/scripts -q`.
9. Guías: `.claude/skills/geo-article/references/` (GEO, estilo humano, plantillas, voz por sitio).
10. Ejemplo completo: `articulos/_ejemplo/` (negocio ficticio, no publicar).
