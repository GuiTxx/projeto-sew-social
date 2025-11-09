# Projeto SEW Social

README em português — guia rápido para entender, rodar e contribuir neste projeto estático.

## Visão geral

Este repositório contém o site estático do projeto "SEW Social". A estrutura prioriza HTML semântico e CSS modular (arquivos por seção). O projeto é uma landing/mini-site com seções como: hero, cursos, grid de mostruário, depoimentos (feedbacks), patrocinadores, entre outras.

Tecnologias usadas
- HTML5
- CSS puro (arquivos organizados em `assets/css/sections/`)
- Arquivos estáticos (imagens, ícones)

## Como visualizar localmente

Opções rápidas (Windows PowerShell):

1) Abrir `index.html` diretamente no navegador
- Simples, funciona para desenvolvimento rápido.

2) Servidor HTTP simples com Python (recomendado para testar caminhos relativos):

```powershell
# a partir da raiz do projeto
python -m http.server 8000
# abra http://localhost:8000 no navegador
```

3) Usar extensão "Live Server" no VS Code — reload automático durante desenvolvimento.

## Organização do repositório (resumo)

Raiz:
- `index.html` — página principal
- `README.md` — este arquivo
- `assets/` — styles, scripts e placeholders
  - `css/` — arquivos CSS
    - `variables.css` — variáveis (cores, fontes)
    - `reset.css` — reset base do projeto
    - `style.css` — estilos globais
    - `sections/` — estilos por seção (cards, cursos, feedbacks, grid-mostruario, etc.)
  - `js/` — scripts (se houver)
- `components/` — fragments/partials HTML (cards, header, footer)
- `images/` — imagens do site (banners, logos, ícones)

Principais arquivos CSS por seção (exemplos):
- `assets/css/sections/grid-mostruario.css` — grid de imagens do mostruário
- `assets/css/sections/feedbacks.css` — depoimentos / cards de feedback
- `assets/css/sections/cursos.css` — cards de cursos
- `assets/css/sections/sponsor.css` — estilos para patrocinadores

## Convenções e notas de estilo

- Variáveis globais em `variables.css` (cores e fontes). Use `var(--nome)`.
- Reset CSS em `reset.css`. Importe-o antes do `style.css`.
- Cada seção tem seu próprio arquivo em `assets/css/sections/` para modularidade.
- Prefira unidades relativas (`rem`, `clamp()`, `max-width`) para responsividade.
- Para espaçamentos entre itens em flex/grid, use `gap` e configure `padding: calc(gap / 2)` no container para que as bordas externas fiquem visualmente iguais ao espaçamento entre itens.

## Problemas observados e recomendações rápidas

- Evitar `top` com valores fixos (ex.: `top: 282rem`). Use centralização com `top:50%` + `transform: translate(-50%, -50%)` e reserve espaço com `padding`/`min-height`.
- Para bordas arredondadas em elementos com `background-image`, usar `::before` com `background-image` e `border-radius: inherit` previne vazamentos.
- Use `font-weight: 700` (numérico) em vez de `bolder` quando precisar de negrito confiável.
- Verifique sempre `grid-template-columns` X `grid-template-areas` nas media queries para evitar desalinhamentos.

## Como contribuir

1. Crie uma branch a partir de `main`: `git checkout -b feat/minha-mudanca`
2. Faça as alterações localmente.
3. Rode o site localmente e verifique responsividade.
4. Commit e push: `git commit -am "feat: descrição"` e `git push origin feat/minha-mudanca`
5. Abra um Pull Request descrevendo as mudanças.

Boas práticas para commits
- Mensagens no formato `feat:`, `fix:`, `chore:`, `style:`.
- Commits pequenos e atômicos facilitam revisão.

## Verificações e testes rápidos
- Teste responsividade com DevTools.
- Verifique paths de imagens (Network tab) se algo não carregar.
- Use validação HTML/CSS para encontrar regras conflitantes.

## Próximos passos sugeridos

- Centralizar variáveis de espaçamento: adicionar `--grid-gap`, `--container-padding` em `variables.css`.
- Otimizar imagens (webp, srcset) e compressão.
- Adicionar lint (stylelint) e checks locais.
- Revisão de acessibilidade (roles, aria, contraste de cores).

## Contato
- Autor/Responsável: Guilherme Teixeira (veja commits no histórico)
