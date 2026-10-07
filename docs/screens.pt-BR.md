# Fluxo · Galeria de telas

[Portfólio](../README.pt-BR.md) · [English](screens.md) · [Estudo técnico](engineering.pt-BR.md)

Doze capturas de um aparelho Android físico mostram a interface do aplicativo e seu manual. Clique em uma imagem para abrir em resolução completa. Os dados dos clientes foram cobertos com tarjas opacas, inclusive os que apareciam através das superfícies de vidro.

## 1. Início e consulta de clientes

<table>
  <tr><th>Tela inicial</th><th>Clientes</th></tr>
  <tr>
    <td><a href="../assets/screens/home.png"><img src="../assets/screens/home.png" width="290" alt="Tela inicial do Fluxo com atalhos e navegação inferior"></a></td>
    <td><a href="../assets/screens/customers.png"><img src="../assets/screens/customers.png" width="290" alt="Lista de clientes com os dados privados cobertos"></a></td>
  </tr>
</table>

A tela inicial dá acesso direto a clientes, pedidos, mensagens e integração. A navegação inferior separa relatórios, início e configurações.

Os cartões dos clientes reúnem informações do cadastro e o tempo desde a última compra. A busca e os filtros ajudam a localizar o cliente antes de iniciar uma visita. As faixas escuras desta captura são tarjas para publicação, não espaços vazios do aplicativo.

## 2. Contexto do cliente e seleção de produtos

<table>
  <tr><th>Detalhes do cliente</th><th>Catálogo de produtos</th></tr>
  <tr>
    <td><a href="../assets/screens/customer-detail.png"><img src="../assets/screens/customer-detail.png" width="290" alt="Cadastro do cliente com ações de visita, ligação, histórico e navegação"></a></td>
    <td><a href="../assets/screens/product-catalog.png"><img src="../assets/screens/product-catalog.png" width="290" alt="Catálogo com imagens e controles de venda e troca"></a></td>
  </tr>
</table>

O detalhamento organiza os campos de cadastro e contato, informa condições de bloqueio e oferece ações de navegação, ligação, histórico e visita.

Na montagem do pedido, cada produto reúne código, nome, foto, quantidade de venda, quantidade de troca e totais. O contexto do cliente continua disponível no topo. A lista respeita os critérios que definem quais produtos podem aparecer, em vez de simplesmente exibir todo o cadastro local.

## 3. Navegação por grupos e quantidade

<table>
  <tr><th>Acesso direto ao grupo</th><th>Diálogo de quantidade</th></tr>
  <tr>
    <td><a href="../assets/screens/product-groups.png"><img src="../assets/screens/product-groups.png" width="290" alt="Grupo de bolos selecionado pelo índice lateral personalizado"></a></td>
    <td><a href="../assets/screens/product-quantity.png"><img src="../assets/screens/product-quantity.png" width="290" alt="Quantidade doze, preço unitário de 5,60 reais e total de 67,20 reais"></a></td>
  </tr>
</table>

Os pontos do índice lateral representam grupos de produtos. Assim, é possível ir a uma categoria sem passar por todos os produtos anteriores. Os cabeçalhos identificam a seção atual; a renderização lazy limita a composição dos itens ao entorno da área visível.

O diálogo de quantidade apresenta o preço e o total durante o preenchimento. Quando há histórico recente do produto para aquele cliente, aparecem sugestões de quantidade sem repetir valores iguais ou mostrar resultados apenas zerados. A captura deste exemplo não possui sugestões de histórico.

## 4. Resumo do pedido e integração

<table>
  <tr><th>Revisão do pedido</th><th>Integração</th></tr>
  <tr>
    <td><a href="../assets/screens/order-review.png"><img src="../assets/screens/order-review.png" width="290" alt="Resumo com pagamento, entrega, observações, itens e ações fixas"></a></td>
    <td><a href="../assets/screens/integration.png"><img src="../assets/screens/integration.png" width="290" alt="Tela de integração com instruções e tempo desde a última atualização"></a></td>
  </tr>
</table>

A revisão reúne condição de pagamento, data de entrega, informações para a nota e itens selecionados. Título e total ficam separados dos detalhes roláveis, assim como as ações de rascunho e finalização. Uma das tarjas também oculta informações do cliente visíveis atrás do diálogo translúcido.

A integração informa a última atualização e orienta a troca de dados com o servidor. O escopo do download depende do grupo do usuário selecionado. **O pedido de exemplo foi descartado; nenhum pedido foi enviado e nenhuma integração foi executada para produzir estas capturas.**

## 5. Ajuda dentro do aplicativo

<table>
  <tr><th>Tópicos do manual</th><th>Estados da integração</th></tr>
  <tr>
    <td><a href="../assets/screens/help.png"><img src="../assets/screens/help.png" width="290" alt="Manual com configuração, navegação, integração, relatórios, pedidos e negociação"></a></td>
    <td><a href="../assets/screens/integration-guide.png"><img src="../assets/screens/integration-guide.png" width="290" alt="Manual explicando andamento, conclusão, alerta, tempo excedido e erro"></a></td>
  </tr>
</table>

A ajuda faz parte do aplicativo. Os tópicos explicam o procedimento e o que fazer diante de cada resultado. Ícones nativos e controles interativos podem acompanhar o tema e a implementação atual dos componentes, sem depender apenas de capturas estáticas.

## 6. Exemplos de negociação · funcionalidade em preparação

<table>
  <tr><th>Exemplo interativo de resposta</th><th>Indicadores conforme o usuário</th></tr>
  <tr>
    <td><a href="../assets/screens/negotiation-guide.png"><img src="../assets/screens/negotiation-guide.png" width="290" alt="Manual de negociação com slider de aprovação ou recusa e botão de reset"></a></td>
    <td><a href="../assets/screens/negotiation-states.png"><img src="../assets/screens/negotiation-states.png" width="290" alt="Manual mostrando os significados dos estados para supervisor e vendedor"></a></td>
  </tr>
</table>

Estas telas são **exemplos didáticos do manual**, não uma caixa de entrada real de supervisor. O slider demonstra o gesto de decisão sem enviar uma resposta de negociação.

O significado de conclusão depende de quem recebe a mensagem. Quando o supervisor responde, sua participação termina tanto na aprovação quanto na recusa. Para o vendedor, a recusa exige uma ação e utiliza um indicador de erro. Uma solicitação ainda sem resposta usa um estado de atenção para o supervisor.

A entrada de negociação para o vendedor permanece desabilitada por flag na versão analisada. Sua presença no manual não significa liberação geral.

## Recursos sem captura de uso real nesta galeria

- **Mensagens:** leitura, arquivamento por gesto, acompanhamento do pedido, detalhes estruturados de negociação e lista–detalhe em larguras maiores. A caixa do usuário selecionado estava vazia durante a captura; não foram criadas mensagens fictícias.
- **Relatórios:** filtros de período, gráficos e apresentação em lista. Os valores comerciais reais foram excluídos desta galeria pública.
- **Layouts maiores:** descritos a partir da implementação. A galeria mostra capturas de celular, não uma sessão de validação em tablet.

Capturas feitas em outubro de 2026 em um Samsung Galaxy A07. A aparência pode mudar entre versões do aplicativo.

[Voltar ao portfólio](../README.pt-BR.md) · [Ler o estudo técnico](engineering.pt-BR.md)
