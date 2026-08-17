# Espaço Zoe — ligar o contador de visitas

Uma página só, feita para **uma pessoa**: o passo a passo para criar a conta do Google
Analytics do site do Espaço Zoe (https://espacozoe.psc.br) e chegar ao código de medição
(aquele que começa com `G-`). Quem abre vai marcando conforme faz, cola o código no campo
do fim, e a página confere se é o código certo antes de ele mandar de volta.

Irmã da página de acompanhamento em
[`espacozoe-checklist`](https://github.com/MenteCriativaIA/espacozoe-checklist), no mesmo
formato e com a mesma identidade visual.

## Por que ela existe

Havia um passo a passo anterior, escrito para ir por WhatsApp, e ele estava errado em dois
pontos. Foi descartado antes de chegar a ser enviado:

1. Dizia que criar a **propriedade** entrega o código `G-`. Não entrega. A propriedade é
   uma pasta vazia; o código só nasce ao criar um **fluxo de dados** do tipo Web dentro
   dela — uma segunda metade inteira que o roteiro antigo nem mencionava. É exatamente o
   ponto onde a tela mostra três botões ("Web", "App Android", "App iOS") e **parece** ter
   terminado.
2. Chamava o campo de "ID de medição". A ajuda oficial do Google em português do Brasil
   chama de [**"ID de métricas"**](https://support.google.com/analytics/answer/12270356?hl=pt-BR),
   e a interface em português de Portugal chama de "ID da métrica". Três nomes para o mesmo
   código, e nenhum deles batia com o que a pessoa via na tela.

Por isso a página ancora no **formato** ("uma linha curta que começa com a letra G e um
tracinho") e na **posição na tela**, nunca só no nome do campo. Todos os rótulos foram
conferidos contra a documentação oficial do Google; onde a documentação não nomeia o botão,
a página descreve onde ele fica em vez de inventar um nome.

## Como ela é feita

- **Sem servidor e sem banco.** O que é marcado, e o código digitado, ficam no navegador de
  quem abriu (`localStorage`). Não sobe para lugar nenhum. Só sai dali quando a pessoa toca
  em "Copiar o código pra me mandar" e cola onde quiser.
- **Sem rastreador, sem cookie, sem fonte externa.** Um arquivo, nada carregado de fora.
  (Sim: a página que serve para instalar um medidor de visitas não tem medidor de visitas.)
- **Fora dos buscadores** (`noindex`) — é uma página para um link direto, não para o Google.
- **Confere o que foi colado** antes de a pessoa mandar, para pegar os três erros comuns:
  o outro identificador (só números), o bloco `gtag` de programação, e o código incompleto.

Este repositório é público porque o GitHub só serve páginas de repositórios públicos no
plano gratuito. Por isso ele contém **apenas** esta página: o projeto do site vive em
repositório privado separado, e nada de dado de paciente, valor de preço ou documento
pessoal entra aqui. O único e-mail que a página oferece é o de quem mantém o projeto, e ele
é montado em pedaços no JavaScript em vez de ficar em texto puro no HTML.
