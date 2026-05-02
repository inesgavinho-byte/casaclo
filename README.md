# Casa Clo — site

Site institucional da Casa Clo, doçaria artesanal em Lisboa e Margem Sul.

Site estático puro (HTML + CSS + JavaScript), sem dependências nem build step.

---

## Estrutura do projecto

```
casa-clo/
├── index.html        ← página principal
├── style.css         ← estilos (cores, layout, responsivo)
├── script.js         ← menu mobile + envio do formulário
├── images/           ← 16 imagens dos doces
├── netlify.toml      ← configuração de cache e segurança
├── .gitignore
└── README.md         ← este ficheiro
```

---

## Como ver o site localmente (no seu computador)

A forma mais simples é abrir o `index.html` no browser com duplo clique.

Se preferir um servidor local (recomendado, porque carrega as fontes do Google sem aviso de CORS):

```bash
# Com Python (já vem instalado em macOS e Linux)
python3 -m http.server 8000

# Depois abrir no browser:  http://localhost:8000
```

---

## Como pôr online via Netlify (passo-a-passo)

### Opção A — drag and drop (mais rápido, sem Git)

1. Vá a [https://app.netlify.com/drop](https://app.netlify.com/drop)
2. Arraste a pasta `casa-clo` inteira para a janela do browser
3. Pronto — o Netlify dá-lhe um URL temporário (ex.: `gentle-tiramisu-12345.netlify.app`)
4. Pode depois ligar um domínio próprio (ex.: `casaclo.pt`) nas definições

### Opção B — via repositório Git (recomendado para actualizar com facilidade)

1. **Criar o repositório no GitHub:**
   - Vá a [github.com/new](https://github.com/new)
   - Nome do repositório: `casa-clo` (ou outro à escolha)
   - Deixe **público** ou **privado** — funciona em qualquer um

2. **Enviar o código (no terminal, dentro da pasta do projecto):**

   ```bash
   git init
   git add .
   git commit -m "primeira versão do site"
   git branch -M main
   git remote add origin https://github.com/SEU-UTILIZADOR/casa-clo.git
   git push -u origin main
   ```

3. **Ligar o repositório ao Netlify:**
   - [app.netlify.com](https://app.netlify.com) → **Add new site** → **Import an existing project**
   - Escolher GitHub e autorizar
   - Selecionar o repositório `casa-clo`
   - Build settings: deixar em branco (o `netlify.toml` já trata de tudo)
   - **Deploy site**

4. **A partir daqui**, sempre que fizer `git push`, o Netlify republica automaticamente.

---

## TODOs antes de lançar publicamente

A versão actual aplica todas as alterações de **alta prioridade** do diagnóstico, mas há ainda alguns pontos pendentes que dependem de informação real ou conteúdo novo:

### Conteúdo a substituir (procurar `TODO` no código)
- [ ] **Email real** — em `index.html` (footer) e em `script.js` (variável `to`)
- [ ] **Instagram** — `https://instagram.com/casaclo` → handle real
- [ ] **WhatsApp** — `https://wa.me/351000000000` → número real (formato internacional, sem `+` nem espaços)

### Páginas legais a criar (links já existem no footer)
- [ ] `termos.html` — Termos e condições de venda
- [ ] `privacidade.html` — Política de privacidade (RGPD)
- [ ] `info-alimentar.html` — Alergénios, conservação, prazos por produto
- [ ] Livro de reclamações electrónico — link já aponta para [livroreclamacoes.pt](https://www.livroreclamacoes.pt/) (criar conta da Casa Clo lá)

### Funcional
- [ ] **Preços** — quando definidos, substituir `Sob encomenda` por `desde X€` em `index.html` (secção `.shop`)
- [ ] **Formulário** — actualmente abre o cliente de email do utilizador. Para receber pedidos directamente, considerar [Netlify Forms](https://docs.netlify.com/forms/setup/) (gratuito, integração nativa) ou [Formspree](https://formspree.io)
- [ ] **Imagem Open Graph** — actualmente usa `images/img-01.jpg`. Idealmente criar uma imagem específica 1200×630 px

### Média prioridade (para uma 2ª iteração)
- Páginas dedicadas para *Eventos* e *Peças especiais*
- SEO: termos como "bolos por encomenda Lisboa", "doces personalizados"
- Imagens em formato WebP/AVIF (menor peso)
- Testar em vários dispositivos (iPhone, Android, tablet)

---

## Dúvidas técnicas

- **As fontes não carregam?** O site usa Google Fonts (CDN externo). Precisa de internet.
- **Quero mudar uma cor?** Editar as variáveis no topo do `style.css` (`:root { --cream: ...; }`).
- **Quero mudar o texto do hero?** Está no `index.html`, dentro de `<section class="hero">`.

---

*Última actualização: 2026-05-02*
