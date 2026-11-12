# simulado-sistemas-distribuidos-11-11

Segue uma versão com pequenas alterações na escrita, mantendo o mesmo sentido, a estrutura e o padrão das respostas originais:

Questão 1. Qual é a função do semáforo no processamento dos pedidos?

O semáforo é responsável por limitar a quantidade de threads que podem executar determinada parte do programa ao mesmo tempo. Neste exercício, ele foi definido para permitir que apenas dois pedidos sejam processados simultaneamente, evitando uma sobrecarga no sistema.

Questão 2. Por que é necessário sincronizar os dados entre o servidor principal e a réplica?

A sincronização permite que a réplica receba as informações atualizadas do servidor principal. Dessa forma, os dois servidores mantêm os dados consistentes, evitando divergências e possibilitando que a réplica seja utilizada caso ocorra uma falha no servidor principal.

Questão 3. O que significa tolerância a falhas e como ela aparece neste programa?

A tolerância a falhas é a capacidade de um sistema continuar funcionando mesmo quando algum componente apresenta problemas. Neste programa, ela ocorre quando o servidor principal fica indisponível e a réplica passa a ser utilizada para realizar as consultas de estoque, mantendo o funcionamento do serviço.

Questão 4. Para que serve o Lock no programa e como o controle de acesso aos recursos ajuda a prevenir problemas de concorrência?

O Lock é utilizado para organizar o acesso das threads aos recursos compartilhados. Com isso, somente uma thread por vez pode realizar determinadas operações, como atualizar o estoque e registrar os pedidos, evitando conflitos, condições de corrida e inconsistências nas informações.

Questão 5. Considerando a sequência de eventos, a sincronização do estoque deve acontecer antes ou depois do processamento dos pedidos? Explique a relação de causalidade.

A sincronização deve ocorrer após o processamento dos pedidos, pois primeiro o servidor principal precisa registrar as vendas e atualizar os valores do estoque. Em seguida, essas informações são enviadas para a réplica. Assim, é mantida a sequência correta dos eventos, garantindo que os dois servidores trabalhem com dados atualizados.
