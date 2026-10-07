![Fluxo — Vinicius Nassif, Desenvolvedor Android](assets/portfolio-cover-pt.svg)

[English](README.md) · [Português](README.pt-BR.md)

# Fluxo · Portfólio de desenvolvimento Android

Sou **Vinicius Nassif**, desenvolvedor Android. Desenvolvo e mantenho o Fluxo, aplicativo utilizado nas operações de vendas externas da **Líder Minas (Milani)**. Meu trabalho envolve implementar funcionalidades, investigar problemas de uso, testar, preparar builds e dar suporte aos usuários.

O Fluxo conecta o trabalho do vendedor — localizar o cliente, selecionar produtos e montar um pedido — aos sistemas de processamento da empresa. A persistência local permite consultar dados já baixados e preparar pedidos sem conexão contínua, respeitando as regras de integração do aplicativo.

**Kotlin · Jetpack Compose · Material 3 · Room / SQLite · Coroutines · StateFlow · Retrofit · Firebase Cloud Messaging**

[Conheça as telas](docs/screens.pt-BR.md) · [Decisões técnicas](docs/engineering.pt-BR.md) · [Sobre mim](docs/about.pt-BR.md) · [Contato](mailto:viniciusbnassif@outlook.com)

## O aplicativo em uso

<table>
  <tr>
    <th>Catálogo de produtos</th>
    <th>Quantidade e preço</th>
    <th>Integração</th>
  </tr>
  <tr>
    <td><a href="assets/screens/product-catalog.png"><img src="assets/screens/product-catalog.png" width="240" alt="Catálogo com fotos, quantidades de venda e troca e índice de grupos"></a></td>
    <td><a href="assets/screens/product-quantity.png"><img src="assets/screens/product-quantity.png" width="240" alt="Diálogo de quantidade com preço unitário e total calculado"></a></td>
    <td><a href="assets/screens/integration.png"><img src="assets/screens/integration.png" width="240" alt="Tela de integração com informação da última sincronização"></a></td>
  </tr>
</table>

As imagens são capturas reais do aplicativo em um aparelho Android, não mockups. Identificadores e informações de contato dos clientes foram cobertos com tarjas opacas. A interface do aplicativo está em português; o portfólio possui versões em português e inglês.

## O que o Fluxo faz

| Área | Uso no dia a dia | Foco da implementação |
| --- | --- | --- |
| Clientes | Pesquisar e filtrar clientes; consultar cadastro, histórico e contato; iniciar uma visita. | Acesso aos dados locais e ações ligadas ao cliente. |
| Catálogo | Consultar produtos com fotos, pesquisar e ir diretamente a um grupo. | Grade lazy, cabeçalhos fixos por seção e índice lateral personalizado. |
| Pedidos | Informar quantidades de venda e troca, conferir preços e condições, salvar rascunho ou finalizar. | Validação, cálculos monetários e persistência local em transação. |
| Sugestões de quantidade | Reaproveitar a menor ou a maior quantidade recente daquele produto para o cliente. | Consulta assíncrona, indicação de carregamento e sugestões sem repetição. |
| Integração | Enviar pendências e atualizar os dados correspondentes ao grupo do usuário selecionado. | Downloads concorrentes, estados por etapa e orientação em caso de falha. |
| Mensagens | Acompanhar o processamento do pedido, consultar detalhes e deslizar para arquivar ou mudar a leitura. | Filtro por usuário, observação do banco e recebimento via FCM. |
| Relatórios | Consultar vendas com filtros de período, gráficos e listas. | Formas diferentes de apresentar os dados da operação. |
| Ajuda | Aprender os procedimentos dentro do app, com indicadores e exemplos interativos. | Reutilização dos próprios componentes da interface no manual. |

### Negociação — em preparação

O Fluxo também possui uma estrutura de negociação de preços entre vendedor e supervisor. Ela inclui os produtos negociados, controles de aprovação e recusa, indicadores conforme o papel de quem recebe a mensagem e uma proteção contra decisões baseadas em listas incompletas de produtos.

**A entrada da negociação para o vendedor está desabilitada por uma flag na versão analisada.** Por isso, ela aparece aqui como uma funcionalidade em preparação, não como um recurso já liberado de forma geral. As capturas dessa parte mostram exemplos do manual, identificados como demonstrações.

## O desenvolvimento por trás das telas

### Salvar localmente antes de transmitir

O pedido e seus itens são gravados juntos em uma transação do Room antes da transmissão. A numeração considera a sequência recebida do servidor e os pedidos locais do usuário selecionado; o número é conferido novamente ao salvar. Isso trata a consistência local sem assumir que o celular, sozinho, garante a unicidade de todos os pedidos no servidor.

### Estado que acompanha o banco

Os fluxos do Room e o `StateFlow` conectam os dados persistidos ao Compose. Isso é importante quando uma mensagem muda depois de aberta, quando o cadastro do usuário selecionado é atualizado ou quando a integração modifica uma lista que já está na tela. As consultas de histórico de produtos também tratam o cancelamento quando a seleção muda.

### Usuários diferentes, integrações diferentes

O grupo do usuário selecionado define o caminho do download: supervisores recebem negociações; os demais usuários recebem os conjuntos de dados comerciais. A regra não depende de descobrir se algum cliente foi baixado. Downloads independentes podem começar em paralelo, mantendo o acompanhamento individual de cada etapa.

### Detalhes da interface ligados ao uso

O índice de produtos navega por grupos, não apenas por uma porcentagem da lista inteira. A tela de mensagens permite uma organização de lista e detalhe em larguras maiores. Controles compartilhados, efeitos de vidro e exemplos interativos do manual são construídos com Compose e bibliotecas de apoio.

[Leia o estudo técnico →](docs/engineering.pt-BR.md)

## Tecnologias e responsabilidades

| Camada | Tecnologias |
| --- | --- |
| Interface | Jetpack Compose, Material 3, layouts adaptativos e controles personalizados |
| Estado e tarefas assíncronas | ViewModel, Kotlin Coroutines, Flow / StateFlow |
| Armazenamento | Room, SQLite e DataStore |
| Comunicação | Retrofit, OkHttp, Gson e Firebase Cloud Messaging |
| Imagens e efeitos | Coil, Haze e componentes Compose compartilhados |
| Verificação e entrega | Testes unitários e de regressão pontuais, testes funcionais, Gradle e releases Android assinadas |

## Contexto do projeto

O Fluxo é um aplicativo de operação comercial com distribuição privada, inclusive em dispositivos Android gerenciados. Este repositório é um **portfólio e estudo de caso técnico**: não contém o código-fonte Android nem um pacote de instalação.

As telas foram capturadas em um Samsung Galaxy A07 físico em outubro de 2026. Nenhum pedido real foi enviado para produzir a demonstração. O comportamento em telas maiores é descrito a partir da implementação; estas capturas não representam testes em tablet.

## Contato

Busco oportunidades em desenvolvimento Android nas quais possa trabalhar em aplicativos úteis, entender suas regras de negócio e continuar melhorando o produto depois da entrega.

**[LinkedIn](https://www.linkedin.com/in/viniciusbnassif) · [GitHub](https://github.com/viniciusbnassif) · [viniciusbnassif@outlook.com](mailto:viniciusbnassif@outlook.com)**

[Experiência profissional e formação →](docs/about.pt-BR.md)
