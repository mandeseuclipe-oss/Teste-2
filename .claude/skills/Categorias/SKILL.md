---
name: Categorias
description: Cria uma nova categoria no site Bruno Sants copiando exatamente a estrutura da categoria principal "Forza Meeting", trocando apenas título, foto principal, fotos do visualizador, fotos do álbum e título do álbum. Use quando o usuário pedir para criar, adicionar ou montar uma categoria nova.
---

# Categorias

A categoria **Forza Meeting** é a categoria principal e serve de modelo. Para criar outra categoria, copie a estrutura inteira do Forza Meeting em `index.html` e troque **somente** o que está listado abaixo.

## O que trocar (e só isso)

1. **Título da categoria** (texto do card na galeria, `<span class="gal-item__title">`).
2. **Foto principal** (o card da galeria: `data-src`, `src` da primeira `<img>` e o `alt`/`aria-label`).
3. **Fotos do visualizador**: as 4 imagens `gal-item__swap` do card (efeito de troca no hover).
4. **Fotos do álbum**: a lista de fotos do álbum no objeto `ALBUMS`, com a chave igual à foto principal da categoria.
5. **Título do álbum**: vem automaticamente do título do card, então basta trocar o título no passo 1.

## O que NÃO mexer

- Nenhum CSS, transição, efeito, parallax, animação, tamanho ou proporção de foto.
- A estrutura do card (`figure.gal-item`, `.gal-item__frame`, `.gal-item__shade`, `.gal-item__title`).
- O rodapé do álbum, o visualizador e o JavaScript.
- Os textos e estilos das outras categorias.

Se algo precisar mudar além dos cinco itens acima, pare e pergunte antes.

## Passo a passo

1. Leia o bloco do Forza Meeting em `index.html`: procure `<figure class="gal-item` com `data-src="assets/img/home-dakota.jpg"` e o `.gal-row` que o contém.
2. Copie esse `.gal-row` inteiro e cole logo abaixo dele, dentro de `.gal`, na ordem em que a nova categoria deve aparecer.
3. Troque os itens 1 a 3 no bloco copiado (título, foto principal e fotos do visualizador). Mantenha o mesmo `style` do `figure` (largura, margem e altura) para que o layout continue igual.
4. Adicione no objeto `ALBUMS` uma nova entrada: a chave é o caminho da foto principal e o valor é a lista de fotos do álbum.
5. As fotos precisam existir em `assets/img/`. Nunca invente imagens: use só as que o usuário enviou. Se o usuário não enviou uma foto, pergunte antes.
6. Confirme que não há erro de sintaxe no JavaScript e que a página abre sem erros no navegador.
7. Faça commit local com a mensagem `Categoria <nome>: nova categoria a partir do modelo Forza Meeting`. Não faça push sem o usuário pedir.
8. Publique o artefato atualizado (mesmo link) e informe o link ao usuário.

## Atenção

- A legenda do visualizador de categoria (função `setCap`) hoje tem um texto fixo, "Exposição de carros e Cosplayers". Ele vale para todas as categorias. Antes de criar a nova, pergunte ao usuário se a nova categoria deve ter o mesmo texto ou um próprio.
- Cada categoria precisa de fotos próprias. Não reutilize as fotos do Forza Meeting, a menos que o usuário peça.
