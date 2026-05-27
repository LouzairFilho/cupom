# Gerador de Cupons para Sorteio

Ferramenta web para criar e imprimir cupons de sorteio (rifas, ações entre amigos) com canhoto destacável. Pensado originalmente para o Departamento Infantil da Igreja Assembleia de Deus 4 de Outubro, mas pode ser usado para qualquer evento — basta trocar os dados pelo painel.

Funciona 100% no navegador, sem servidor, sem instalação.

## Como usar

1. Abra o arquivo `gerador-cupom.html` no navegador (Chrome ou Edge recomendados — duplo clique no arquivo).
2. À esquerda aparece o **painel de edição**; à direita a **prévia da folha A4** com os cupons.
3. Preencha os campos do painel — a prévia atualiza ao vivo enquanto você digita.
4. Quando estiver pronto, clique em **🖨️ Imprimir / PDF** para imprimir em papel ou salvar como PDF.

> **Dica de impressão:** no diálogo de impressão, em "Mais configurações", marque **Gráficos de plano de fundo** para sair com as cores. Desmarque **Cabeçalhos e rodapés**.

## O que dá para personalizar

### Textos do cupom
- **Título** (ex: "Departamento Infantil")
- **Subtítulo** (ex: "Adoradores Kids" — deixe vazio para esconder)
- **Prêmio** (ex: "Chaleira Elétrica 1,7L")
- **Data do sorteio**
- **Local**
- **Valor do cupom**

### Rodapé
- **Versículo / frase** — deixe vazio para não mostrar nada no rodapé.

### Imagens do prêmio
- Faça upload de até **2 imagens** do prêmio (JPG, PNG, WEBP).
- Se enviar só uma, ela aparece em destaque.
- Se enviar duas, aparecem lado a lado.

### Aparência
- **Cor principal** — define cor das bordas, linhas do canhoto e ícones.
- **Cupons por folha** — 4 (maiores), 5 (recomendado) ou 6 (menores).
- **Fundo do cupom** — 9 opções:
  - Padrão (amarelo + rosa suave)
  - Branco limpo
  - Listrado pastel
  - Gradientes (azul, amarelo, rosa, verde)
  - Cor sólida (você escolhe pelo color picker)
  - Imagem de fundo (upload, com camada branca translúcida automática para o texto ficar legível)

## Botões do painel

| Botão | O que faz |
|-------|-----------|
| 🖨️ **Imprimir / PDF** | Abre o diálogo de impressão. Escolha "Salvar como PDF" para gerar arquivo. |
| 💾 **Salvar** | Guarda a configuração atual no navegador (localStorage). |
| 📂 **Carregar** | Restaura a última configuração salva. |
| 🔄 **Resetar tudo** | Apaga configuração salva e volta aos valores padrão. |

## Limitações importantes

- **Imagens não são salvas no localStorage** (são grandes demais). Toda vez que abrir o gerador, será necessário fazer upload das imagens novamente. Textos, cor, fundo e quantidade ficam salvos normalmente.
- **Configuração é por navegador**: o "Salvar" guarda no navegador atual. Se abrir em outro dispositivo, começa do zero.
- **Sem login / sem nuvem**: tudo roda local, nada é enviado para servidores.

## Estrutura dos arquivos

```
cupom/
├── gerador-cupom.html      ← arquivo principal (abra este)
├── cupom-infantil.html     ← versão estática original (5 cupons fixos)
├── premio1.webp            ← imagem do prêmio (chaleira em uso)
├── premio2.webp            ← imagem do prêmio (caixa)
└── README.md               ← este arquivo
```

## Como o cupom é estruturado

Cada cupom tem duas partes separadas por uma linha pontilhada vertical:

- **Canhoto (esquerda)** — fica com a organização. Tem campos para preencher à mão: Nome, Telefone, Vendedor.
- **Cupom (direita)** — fica com o comprador. Mostra título, subtítulo, imagens do prêmio, dados (prêmio/sorteio/local/valor) e versículo no rodapé.

Após imprimir, corte as linhas horizontais entre os cupons e a linha pontilhada vertical entre canhoto e cupom (no momento da venda).

## Publicação online

Por ser um único arquivo HTML estático, pode ser hospedado gratuitamente em qualquer serviço de site estático:

- **GitHub Pages** — suba os arquivos para um repositório público e ative em Settings → Pages.
- **Netlify Drop** — arraste a pasta em https://app.netlify.com/drop, gera URL na hora.
- **Cloudflare Pages**, **Vercel** — opções similares, também gratuitas.

Para abrir direto pela URL raiz (sem precisar digitar o nome do arquivo), renomeie `gerador-cupom.html` para `index.html` antes de publicar.

## Tecnologias

HTML, CSS e JavaScript puros. Sem frameworks, sem build, sem dependências externas. Roda offline depois de carregado uma vez.
