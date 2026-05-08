# Design Reference - Agroprocess

Identidade visual da divisão Agroprocess (Setbox). Paleta Sicredi (verde cooperativo).

---

## Identidade Visual

**Filosofia:** Editorial minimalista. Swiss/International typographic style. Quase zero ornamento, todo o trabalho estético é feito por tipografia, espaçamento e uso cirúrgico da cor de destaque.

**Paleta base:**

| Token | Valor | Uso |
|---|---|---|
| `bg` | `#FAFAFA` | Fundo padrão |
| `text` | `#111111` | Texto primário |
| `text-muted` | `#555555–#888888` | Texto secundário |
| `border` | `#E5E5E5` | Divisores, bordas de card |

**Paleta accent (Agroprocess):**

| Token | Valor | Uso |
|---|---|---|
| `accent` | `#3FA110` | CTAs, labels de seção, ícones, nav ativo |
| `accent-hover` | `#146E37` | Hover de botões primários |
| `accent-dark` | `#146E37` | Fundo de seção CTA final |
| `accent-lt` | `#F2F9ED` | Fundo de ícone em card, seções sutis |
| `yellow` | `#FFCD00` | Botão de destaque sobre fundo verde escuro |
| `neutral-lt` | `#D7E6C8` | Bordas de cards em seções com fundo verde |
| `neutral` | `#5A645A` | Texto secundário em contexto agro |

---

## Tipografia

**Font stack:** Inter via Google Fonts (optical size 14..32, pesos 300-800).

| Nível | Tamanho | Peso | Uso |
|---|---|---|---|
| Display | 48-52px | 800 | H1 hero |
| H2 | 26-38px | 700 | Títulos de seção |
| H3 | 16-17px | 600 | Cabeçalhos de card |
| Body | 15-17px | 400 | Parágrafos |
| Small | 13px | 400-500 | Labels, bullets |
| Caption | 12px | 400 | Footer, legendas |
| Label | 11px | 600 | Labels de seção (uppercase) |

**Labels de seção:**
```html
<p class="text-[11px] font-semibold tracking-wide uppercase mb-3" style="color:#3FA110;">Label</p>
```

---

## Layout e Grid

**Max width:** `max-w-5xl` (1024px). **Padding:** `px-4 md:px-8`. **Container inner:** `max-width:1024px; margin:0 auto; padding:0 32px`.

Two-col: `display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:center`

Three-col: `display:grid;grid-template-columns:repeat(3,1fr);gap:16px`

---

## Componentes

### Navbar

```
[Agroprocess]    Soluções  Para quem  [Solicitar demonstração]
```

- Sticky top, `bg-[#FAFAFA]`, `border-b border-[#E5E5E5]`, `h-14`, `z-50`
- Logo: `text-[17px] font-bold tracking-tight color:#3FA110`
- Links: `text-sm text-[#111111] hover:opacity-50 transition-opacity hidden md:block`
- CTA: `bg-[#3FA110] text-white px-4 py-1.5 rounded-[6px] hover:bg-[#146E37]`

### Botão Primário

```html
<a href="mailto:contato@setbox.com.br?subject=Agroprocess - Solicitar demonstração"
   class="inline-block text-[14px] text-white px-6 py-3 rounded-[6px] font-semibold transition-colors"
   style="background:#3FA110;"
   onmouseover="this.style.background='#146E37'" onmouseout="this.style.background='#3FA110'">
  Solicitar demonstração
</a>
```

### Botão Destaque (sobre fundo verde escuro)

```html
<a href="..." style="background:#FFCD00;color:#111111;"
   onmouseover="this.style.background='#e6b800'" onmouseout="this.style.background='#FFCD00'"
   class="inline-block text-[14px] font-semibold px-6 py-3 rounded-[6px] transition-colors">
  CTA
</a>
```

### Card

```html
<div class="border border-[#E5E5E5] rounded-xl bg-white p-6">...</div>
```

Card em seção verde: `border-[#D7E6C8]`

### Ícone de card

```html
<div style="width:32px;height:32px;border-radius:8px;background:#F2F9ED;display:flex;align-items:center;justify-content:center;margin-bottom:16px;">
  <svg width="18" height="18" ... stroke="#3FA110" .../>
</div>
```

### Bullets

```html
<li class="flex gap-3 text-[13px] text-[#444444]">
  <span class="font-bold flex-shrink-0" style="color:#3FA110;">→</span>
  Texto do item
</li>
```

### Status badge

```html
<!-- Lento -->
<span style="padding:3px 8px;border-radius:9999px;background:#fef9c3;border:1px solid #fde047;color:#713f12;" class="text-[11px] font-semibold">LENTO</span>
<!-- Conflito -->
<span style="padding:3px 8px;border-radius:9999px;background:#fef2f2;border:1px solid #fecaca;color:#991b1b;" class="text-[11px] font-semibold">CONFLITO</span>
```

### Footer

```html
<footer class="border-t border-[#E5E5E5]">
  <div class="max-w-5xl mx-auto px-4 md:px-8 py-10 md:py-14">
    <a href="https://setbox.com.br" target="_blank"><img src="assets/setbox-lateral.png" alt="Setbox" class="h-6 w-auto mb-5" width="1405" height="466"></a>
    <p class="text-[12px] text-[#BBBBBB] mb-1">© 2026 Setbox Serviços Digitais</p>
    <p class="text-[12px] text-[#BBBBBB]">Rua João Bettega, 649 - Sala 3A<br>Curitiba / PR</p>
  </div>
</footer>
```

---

## Tom Visual Geral

- **Zero decoração:** sem gradientes, sem shadows, sem ilustrações, sem stock photos
- **Hierarquia por tamanho e peso:** cor de destaque usada com parcimônia
- **Densidade baixa:** uma ideia por bloco, muito espaço entre seções
- **Confiança editorial:** conteúdo fala sozinho, design não grita
