# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Development

No build step. Open `index.html` directly or serve with `npx serve .` / `python3 -m http.server 8080`. Tailwind CSS and Inter load via CDN.

## Architecture

Single-page static site for **Agroprocess** (agroprocess.com.br) — automação de processos operacionais do agronegócio, uma divisão da Setbox Sistemas Digitais. All assets in `assets/`. See `DESIGN.md` for component patterns.

## Nav

Logo: `assets/agroprocess.png` (`h-8 w-auto`, width=467 height=245), links to `/`.

Order: `[Agroprocess]` | Soluções | Para quem | `[Solicitar demonstração]` (CTA).

Active link: `font-medium style="color:#3FA110;"`. Inactive: `text-sm text-[#111111] hover:opacity-50 transition-opacity hidden md:block`.

CTA "Solicitar demonstração" links to `mailto:contato@setbox.com.br?subject=Agroprocess - Solicitar demonstração`, style: `background:#3FA110` hover `#146E37`.

Standalone site — no Setbox navbar links.

## Footer

Logo Setbox (`assets/setbox-lateral.png`, `h-6 w-auto`, links to `https://setbox.com.br` `target="_blank"`) + © 2026 Setbox Serviços Digitais + endereço. Sem colunas adicionais.

```html
<footer class="border-t border-[#E5E5E5]">
  <div class="max-w-5xl mx-auto px-4 md:px-8 py-10 md:py-14">
    <a href="https://setbox.com.br" target="_blank"><img src="assets/setbox-lateral.png" alt="Setbox" class="h-6 w-auto mb-5" width="1405" height="466"></a>
    <p class="text-[12px] text-[#BBBBBB] mb-1">© 2026 Setbox Serviços Digitais</p>
    <p class="text-[12px] text-[#BBBBBB]">Rua João Bettega, 649 - Sala 3A<br>Curitiba / PR</p>
  </div>
</footer>
```

## Asset Paths

All assets use root-relative paths: `assets/filename.ext`. No `../../` prefixes — standalone repo.

| Arquivo | Caminho |
|---|---|
| Logo Agroprocess | `assets/agroprocess.png` (467x245) |
| Logo Setbox (footer) | `assets/setbox-lateral.png` |
| Favicon ICO | `assets/favicon.ico` |
| Favicon 32x32 | `assets/favicon-32x32.png` |
| Favicon 16x16 | `assets/favicon-16x16.png` |
| Apple touch icon | `assets/apple-touch-icon.png` |

## Content Rules

- Language: Brazilian Portuguese
- No trailing period on any title or subtitle (h1-h6)
- Never use em dash anywhere — use hyphen (-) or comma
- Contact email: `contato@setbox.com.br`
- Domain: `agroprocess.com.br`

## Image Rules

- All `<img>` must have `width`, `height`, and `loading="lazy"` — except nav/footer logos (above fold)

## Color Palette (Agroprocess)

| Token | Valor | Uso |
|---|---|---|
| `accent` | `#3FA110` | CTAs, labels de seção, ícones, nav ativo |
| `accent-hover` | `#146E37` | Hover de botões primários |
| `accent-dark` | `#146E37` | Fundo de seção CTA final |
| `accent-lt` | `#F2F9ED` | Fundo de ícone em card, seções sutis |
| `yellow` | `#FFCD00` | Botão de destaque sobre fundo verde escuro |
| `neutral-lt` | `#D7E6C8` | Bordas de cards em seções com fundo verde |
| `neutral` | `#5A645A` | Texto secundário em contexto agro |

Labels de seção: `text-[11px] font-semibold tracking-wide uppercase" style="color:#3FA110;"`

Bullets: `<span class="font-bold flex-shrink-0" style="color:#3FA110;">→</span>`

## SEO

Every page needs: `meta[description]`, `link[canonical]`, Open Graph tags (`og:type/site_name/locale/url/title/description/image`), Twitter card. OG image: `assets/og-image.png` (1200x630). `og:site_name` = "Agroprocess". Tailwind CDN: add `<link rel="preload" as="script">` before the `<script>` tag.
