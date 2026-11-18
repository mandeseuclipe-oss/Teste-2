---
name: Categorias
description: Cria uma nova categoria no site Bruno Sants copiando exatamente a estrutura da categoria principal "Forza Meeting", trocando apenas título, foto principal, fotos do visualizador, fotos do álbum e título do álbum. Use quando o usuário pedir para criar, adicionar ou montar uma categoria nova.
---

# Categorias

A categoria **Forza Meeting** é a categoria principal e é o modelo. Para criar outra categoria, copie a estrutura inteira do Forza Meeting em `index.html` e troque **somente** o que está listado abaixo.

## O que trocar (e só isso)

1. **Título da categoria**: o texto de `<span class="gal-item__title">` do card.
2. **Foto principal**: `data-src`, o `src` da primeira `<img>` e o `alt` / `aria-label` do card.
3. **Fotos do visualizador**: as 4 imagens `gal-item__swap` do card (troca no hover).
4. **Fotos do álbum**: a lista no objeto `ALBUMS`, com a chave igual à foto principal da categoria.
5. **Título do álbum**: vem do título do card, então basta trocar o título no passo 1.

## O que NÃO mexer

- CSS, transições, efeitos, animações, parallax, tamanhos e proporções de foto.
- A estrutura do card: `figure.gal-item`, `.gal-item__frame`, `.gal-item__shade`, `.gal-item__title`.
- Rodapé do álbum (bloco `footer.alb-foot`): textos, links, ícones e legenda ficam iguais.
- Botões do álbum: casinha (`#albHome`) e seta de retorno (`#albClose`).
- Visualizador: zoom de 1x a 1.5x, arraste para trocar de foto, degradê que acompanha a foto.
- Bloqueio de download das fotos (já vale para o site inteiro).
- JavaScript.

Se algo precisar mudar além dos cinco itens acima, pare e pergunte antes.

## Passo a passo

1. Em `index.html`, ache o card do Forza Meeting: `<figure class="gal-item` com `data-src="assets/img/home-dakota.jpg"` e o `.gal-row` que o contém.
2. Copie esse `.gal-row` inteiro e cole logo abaixo dele, dentro de `.gal`, na ordem em que a categoria deve aparecer.
3. No bloco copiado, troque título, foto principal e fotos do visualizador. Mantenha o `style` do `figure` (largura, margem e altura).
4. Adicione uma entrada em `ALBUMS`: chave = caminho da foto principal, valor = lista de fotos do álbum.
5. As fotos precisam existir em `assets/img/`. Nunca invente imagens: use só as que o usuário enviou. Se faltar foto, pergunte antes.
6. Confira a sintaxe do JavaScript e abra a página no navegador sem erros.
7. Faça commit local com a mensagem `Categoria <nome>: nova categoria a partir do modelo Forza Meeting`. Não faça push sem o usuário pedir.
8. Publique o artefato atualizado (mesmo link) e informe o link ao usuário.

## Configurações atuais do Forza Meeting (modelo)

Estas são as configurações que a categoria principal tem hoje. Ao copiar, mantenha tudo isso.

**Card na galeria**
- `figure` com `style="width:62%;margin-left:4%;margin-top:0;"`. Cada categoria fica em sua própria `.gal-row`.
- Layout em zigue-zague: a categoria seguinte pode usar `margin-left:34%;margin-top:160px;` para ficar à direita e mais abaixo (é o único ajuste de posição permitido).
- Efeito de card ao rolar (JS, na linha da revelação de `.gal-row`): entra com `rotationX: 14`, `scale: .93`, `opacity: .35`, e assenta até o normal ao chegar a `top 84%`. Reverte ao subir.
- Revelação de cada foto (`.gal-item`): sobe e aparece com `y: 60`, em sequência por linha. Não mexer.
- Troca de fotos ao passar o cursor (só com mouse): roda para todas as categorias, usando as 4 `gal-item__swap`. A capa aparece primeiro.
- Parallax vertical do card: amplitudes em `galAmps`. Não mexer.
- Texto do título: `<span class="gal-item__title">` aparece no card e é o título do álbum.

**Visualizador (ao clicar na categoria)**
- Legenda: título da categoria + "Exposição de carros e Cosplayers" (texto fixo na função `setCap`).
- Zoom de 1x a 1.5x (roda do mouse e duplo clique). Arrastar foto ampliada move a imagem, com limite de margem.
- Arrastar para o lado troca de foto. O degradê preto de baixo acompanha a foto durante o arraste e volta junto ao soltar.
- Veja mais e setas seguem o padrão do modelo.

**Álbum (Veja mais)**
- Título vem do card. Fotos vêm de `ALBUMS`, com a chave igual à foto principal. Sem fotos, mostra "Fotos do álbum em breve."
- Casinha (`#albHome`, canto superior esquerdo): fecha tudo com o loading da logo e volta ao topo da home.
- Seta de retorno (`#albClose`, canto superior direito): loading da logo, fecha o álbum e a foto ampliada, e a página volta a rolar.
- Botão Voltar do navegador fecha o álbum.
- Parallax das fotos do álbum e sem desfoque ao rolar.
- Rodapé (`footer.alb-foot`), com esta ordem:
  - "Vamos fazer uma foto?" (título, em duas linhas).
  - Legenda: "Registre seus melhores momentos, experiências e novidades agora! Clique e tenha sempre algo pra lembrar daquele momento de maneira nostálgica."
  - Linha de links, distribuída na largura: e-mail `brunosantsjob@gmail.com` (com ícone de envelope), WhatsApp (`https://wa.me/5511921248816`, texto "whatsapp", com ícone), Banlek (`https://banlek.com/brunosantsfotografias`, texto "Banlek", com ícone de câmera).
  - Barra de baixo: "© 2026 Bruno Sants" e "Retratos · Automotivo".
  - Títulos, textos e links têm cor preta. Entrada com fade ao rolar, de baixo para cima.
  - Ocupa a largura do site e encosta na base do álbum.

**Global (vale para todas as categorias)**
- Bloqueio de download: clique direito, arrastar e seleção de imagens ficam desativados.

## Atenção

- A legenda do visualizador é definida na função `setCap` e é a mesma para todas as categorias. Antes de criar a nova, pergunte se ela deve ter o mesmo texto ou um próprio.
- Cada categoria precisa de fotos próprias. Não reutilize as fotos do Forza Meeting, a menos que o usuário peça.
