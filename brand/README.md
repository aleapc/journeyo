# Identidade visual — Journeyo

Mascote: um guaxinim (esperto, curioso, "sabe as manhas locais") dentro de uma
marca em formato de balão de fala. Paleta de marca (ver `tailwind.config.js`
do PWA): terracota `#C84B31`, sol `#ECB365`, oceano `#2D6E7E`, creme `#FFF7EC`,
carvão `#2B2B2B`, salvia `#7FA98C`.

## Estrutura

- `source/` — as peças originais geradas (alta resolução, não editar). Ponto
  de partida para qualquer nova derivação.
  - `mascote-icone-transparente.png` — ícone (rosto no balão), fundo transparente.
  - `mascote-icone-quadrado.png` — o mesmo, recortado e centralizado num
    canvas quadrado com margem — é o MASTER usado para gerar todos os ícones.
  - `mascote-corpo-inteiro.png` — guaxinim de corpo inteiro, acenando, fundo
    transparente. Para telas de boas-vindas do app e screenshots de loja.
  - `banner-feature-graphic.png` — cena larga (guaxinim chegando a um lugar
    novo, porta em arco), fundo creme, sem texto. Base para banners/redes
    sociais/feature graphic.
- `web/` — favicons e ícones PWA (fundo transparente):
  `favicon-16.png`, `favicon-32.png`, `favicon-48.png`,
  `apple-touch-icon-180.png`, `icon-192.png`, `icon-512.png`, `icon-1024.png`.
- `ico/journeyo.ico` — ícone multi-resolução (16/32/48/256) para desktop/Windows.
- `app-icons/` — ícones OPACOS (fundo creme sólido, sem transparência —
  exigência da Apple/Google para o ícone principal do app):
  - `ios-appstore-1024.png` — App Store Connect / ícone do app iOS (1024×1024).
    O Xcode gera todos os tamanhos menores automaticamente a partir deste.
  - `android-playstore-512.png` — ícone de alta resolução do Play Console (512×512).
- `android-adaptive/` — para o ícone adaptativo do Android (Android Studio):
  - `foreground-432.png` — camada de frente, transparente, com margem de
    segurança (conteúdo ocupa a região central, como exige o formato adaptativo).
  - `background-432.png` — camada de fundo, cor sólida creme `#FFF7EC`
    (pode usar direto o hex no Android Studio em vez do arquivo).
- `marketing/feature-graphic-1024x500.png` — banner no tamanho exato exigido
  pelo Google Play Console (Store listing → Graphics → Feature graphic).

## Uso na landing page

`img/logo-mark.png`, `favicon-16.png`, `favicon-32.png` e
`apple-touch-icon.png` na raiz do site (`kit-de-bordo/`) são cópias das
versões em `brand/web/` — mantidas fora de `brand/` porque o GitHub Pages
publica a partir da raiz do repositório.

## Gerando novos tamanhos

Os scripts que produziram este kit (recorte, redimensionamento, .ico,
achatamento em fundo sólido) estão documentados na sessão que os criou —
qualquer PNG novo em `source/` pode passar pelo mesmo pipeline: recortar ao
conteúdo → centralizar num quadrado com margem → redimensionar por
interpolação bicúbica → achatar em creme quando o destino exigir opacidade.
