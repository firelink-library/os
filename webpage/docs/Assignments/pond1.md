---
title: P1 - Criando um kernel
sidebar_position: 1
slug: /pond1
---

# Criando um kernel simples

## 1. Enunciado

**O que?**

Nesta ponderada, você precisará criar um micro kernel de sistema operacional.

Isso significa:

* Criar um *bootloader* em assembly que chama uma função externa. Essa função
  externa vai ser efetivamente o loop principal do *kernel*. Você pode usar a
  linguagem de progração que quiser para definir essa função externa, mas
  recomenda-se fortemente o uso de **C**. 
* O seu kernel deve ser capaz de exibir caracteres em tela.
* O seu kernel deve ser capaz de interagir com as interrupções da CPU para
  fazer a leitura das teclas digitadas no teclado.
* Por fim, a aplicação do seu kernel deve ser um jogo interativo simples. O
  jogo pode ser algo já existente (e.g. forca, termo) ou de sua autoria.

**Como?**

Sugere-se o uso do **qemu** para não precisar se preocupar com suporte de
hardware real para o seu kernel.

**Especificações de entrega**

Envie o link do repositório do seu micro kernel no card. Nele, espera-se que
haja um *README* com a explicação do que foi feito e de como rodar o projeto e
um **vídeo** que deve ser mais do que apenas uma demonstração do sistema, mas
sim **uma explicação do que foi feito e como**. Este vídeo não deve ter mais do
que 10 minutos de duração. Caso ache que precise de mais tempo, me consulte
antes de enviar a atividade.

**Padrão de qualidade**

Ser capaz de fazer um kernel capaz de exibir caracteres na tela do usuário vale
**até 4 pontos**.

Ser capaz de interagir corretamente com as interrupções da CPU e ler as teclas
digitadas pelo usuário vale **até 3 pontos**.

A lógica e implementação do jogo vale **até 4 pontos**. Você pode escolher o
nível de complexidade do jogo que vai implementar. Uma experiência interativa
muito simples vai valer menos nota do que um jogo mais complexo. Sinta-se à
vontade para validar comigo a lógica do jogo e verificar se a sua implementação
correta vale **4 pontos** ou menos.
