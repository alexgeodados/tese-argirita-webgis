# WebGIS da tese — Argirita/MG

Atlas interativo de Alex Santos, preparado a partir de `Argirita_v05_escalas_padronizadas.qgz` em 20/10/2026.

## Publicar no GitHub Pages

1. Abra https://github.com/alexgeodados/tese-argirita-webgis e escolha **Add file → Upload files**.
2. Envie o CONTEÚDO desta pasta: `index.html`, `app.js`, `style.css`, `.nojekyll`, e as pastas `data`, `assets` e `vendor`. Não envie o ZIP como substituto dos arquivos. O `index.html` deve ficar na raiz do repositório.
3. Confirme o envio em **Commit changes**.
4. Em **Settings → Pages**, escolha **Deploy from a branch**, branch **main**, pasta **/(root)** e **Save**.
5. Aguarde a publicação. O endereço esperado, se o proprietário e o repositório mantiverem esses nomes, é https://alexgeodados.github.io/tese-argirita-webgis/ .

Este pacote foi preparado localmente. Sua existência não confirma publicação no GitHub.

## Conteúdo e métodos

- 220 unidades amostrais; sete temas vetoriais: IC, IR, P–S–V, P, S, V e U.
- Quatro superfícies raster: estimativas de IC e IR por krigagem e respectivos erros-padrão.
- Limite municipal, máscara do suporte geoestatístico, drenagem, vias, cidade e localidades.
- Geometrias vetoriais convertidas para longitude/latitude (EPSG:4326). Imagens raster renderizadas em EPSG:3857 com os renderizadores do projeto QGIS, exportadas como PNG transparente de 1.400 pixels de largura.
- Cores, classes e opacidades de preenchimento extraídas do QGIS. Contornos, rótulos, layouts de impressão e comportamento por escala foram adaptados para navegação web; esta página não é reprodução exata dos layouts de impressão.
- A consulta às unidades usa `id_amostra`, `sample_id`, `p_aud_final`, `s_aud_final`, `v_aud_final`, `u_aud_final`, `ic_aud_final`, `ir_aud_final`, `classe_ic_aud_final` e `classe_ir_aud_final`. Notas e campos de auditoria operacional foram excluídos.
- As superfícies são visualizações; não permitem obter valores numéricos por pixel nem substituem os GeoTIFFs para análise.
- As células observadas não representam cobertura contínua de todo o município. Consulte o suporte geoestatístico ao interpretar as estimativas.
- Contexto territorial: arquivos BC250/IBGE (2025) presentes no projeto. Limite municipal conforme a camada `aoi_area_de_interesse` do projeto.

## Dependências e autoria

Leaflet 1.9.4 incluído em `vendor`, sob licença BSD-2-Clause (arquivo de licença incluído). A página inicia com fundo claro e dados locais; OpenStreetMap é opcional, depende de internet e mantém a atribuição. Não foram incorporados os serviços Google Satellite ou World Imagery do QGIS.

Os dados científicos não receberam uma licença de redistribuição por esta preparação. A licença do Leaflet se aplica exclusivamente à biblioteca. Revise a autorização de divulgação dos dados antes da publicação pública.

## Prévia local

Sirva esta pasta por HTTP; abrir `index.html` diretamente com duplo clique pode bloquear o carregamento dos dados. Uma opção, com Python instalado, é executar `python -m http.server 8765` nesta pasta e abrir http://localhost:8765 .
