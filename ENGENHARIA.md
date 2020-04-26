<details>
  <summary>## Reunião #1 com o cliente 2020-mar-07</summary>

  Estes são os rabiscos da reunião com o João, O Bigodudo para a criação de um sistema para ele.

  João contou que o <strong>problema</strong> identificado por ele é que os clientes estão se acumulando do lado de fora da barbearia, formando fila, o que faz com que muitos desistam do atendimento. Ele perguntou se conheço alguma solução para ajudá-lo. Como os salões fazem? O que os concorrentes têm que ele ainda não sabe?

  <strong>Sugeri a ideia de criar uma agenda</strong>, em forma de aplicativo, para que cada cliente tenha seu próprio horário e cheguem somente no tempo correto, evitando assim filas e desistências.

  O João gostou da ideia e conversamos sobre <strong>algumas funcionalidades básicas</strong> que o aplicativo teria.

  1. autenticação, precisamos que o cliente que marcou o horário seja ele mesmo;
  2. agenda, cada cliente poderá marcar seu próprio horário, e poderá cancela-lo também;
  3. avaliação, cada cliente avaliará o serviço prestado;
  4. notificação, o cliente receberá um aviso de que seu horário está próximo;

  João me perguntou sobre o preço para o desenvolvimento e se eu poderia entrega-lo na próxima semana, dia 14. Respondi que não pois ainda <strong>precisamos refinar esses requisitos e melhorar o entendimento das necessidades</strong> dele. <strong>Deixei claro que se ele lembrasse de mais alguma</strong> coisa poderia me ligar ou mandar um e-mail.

  Dei o nome "Barba-e-ria" para o projeto. Achei engraçado.
</details>

<details>
  <summary>## Reunião #2 com o cliente 2020-mar-14</summary>

Estes são os rabiscos da segunda reunião com o João, O Bigodudo para a criação de um sistema para ele.

Esse foi uma semana bem agitada, João me ligou várias vezes dizendo que estamos subestimando o aplicativo e pediu mais funcionalidades (adeus sistema simples, fácil e rápido).

Hoje voltei a falar com ele para apresentar a <strong>lista de requisitos</strong> identificados, e já <strong>classificados (entre funcional e não funcional)</strong>, e saber se está de acordo com o que ele tem em mente. A lista dos requisitos são:

  1. RF01 - alto - essencial - marcar horário, cada cliente poderá marcar seu próprio horário escolhendo em um calendário o horário livre. Saberemos a janela necessária pois os serviços prestados pela barbearia já estarão pre-cadastrados e os barbeiros também;
  2. RF02 - médio - importante - cancelar horário, tanto o cliente quanto o barbeiro escolhido podem cancelar um horário quando quiserem, sem restrição.
  3. RF03 - médio - importante - avaliar serviço, cada cliente avaliará o serviço prestado;
  4. RF06 - baixo - desejável - notificar agendamento, o cliente receberá um aviso, pelo aplicativo, de que seu horário está próximo;
  5. RF04 - médio - importante - verificar histórico, o cliente ou o barbeiro poderão ver todos os agendamentos passados ou futuros dele;
  6. RF05 - baixo - desejável - salvar perfil, o cliente poderá atualizar suas informações no aplicativo.
  7. RNF03 - alto - essencial - plataforma, o aplicativo deve funcionar em IOS e Android;
  8. RNF04 - médio - essencial - layout, deve seguir a identidade da barbearia;
  9. RNF01 - alto - importante - autenticar usuário, precisamos que o cliente que marcou o horário seja ele mesmo. Não deve ser armazenado login e senha;
  
  Após apresentar a lista de requisitos, João concordou com essa lista e concluímos <strong>o escopo</strong> do sistema. Estamos prontos para prosseguir e pedi para o João classificar a prioridade desses requisitos e qual <strong>a importância</strong> de cada um deles.
</details>

<details>
  <summary>## Preparação para a reunião #3 (parte 1/3) - prototipo - 2020-mar-21</summary>

Como os requisitos foram levantados corretamente (até o momento), comecei a fazer um protótipo de baixa fidelidade (para não ocupar muito meu tempo).
O protótipo foi realizado com uma ferramenta online, apenas para que o cliente tenha uma ideia das principais funcionalidades do aplicativo (aqueles marcados como essenciais ou importantes). Assim, teremos aumentaremos a certeza sobre os principais pontos do sistema.

<table>
  <tr>
    <td><img src="engenharia/login.png" title="login"/></td>
    <td><img src="engenharia/agendamento.png" title="agendamento"/></td>
  </tr>
  <tr>
    <td>Tela de Login</td>
    <td>Tela de Agendamento</td>
  </tr>  
  <tr>
    <td><img src="engenharia/agenda-barbeiro.png" title="agenda barbeiro"/></td>
    <td><img src="engenharia/avaliação.png" title="avaliação"/></td>
  </tr>
  <tr>
    <td>Tela de Agenda do Barbeiro</td>
    <td>Tela de avaliação</td>
  </tr> 
  </table>
  
  Embora o cliente não tenha solicitado login por Facebook, Google ou Twitter... acredito que será uma boa surpresa.
</details>

## Preparação para a reunião #3 (parte 2/3) - cenários de uso - 2020-mar-28

Para garantir o entendimento de cada requisito, foi descrito o _cenário de uso_ de cada um deles com o maior número de detalhes possível.

* UCC#01: marcar horário - ref. RF#01

  Um cliente pode marcar um horário específico para ser atendido. Para tal, este usuário deve estar autenticado, escolher um barbeiro e um serviço que deseja de uma lista pré-determinada. Depois da escolha é apresentado todos os horários livres do barbeiro escolhido, já calculada a janela de tempo necessária para a execução do serviço. Os serviços, os barbeiros e o tempo de execução e preço de cada serviço já estará pré-cadastrada no sistema e não será possível sua alteração, adição ou exclusão (caso necessário, somente o desenvolvedor poderá faze-los).

* UCC#02: cancelar horário - ref. RF#02

  Tanto o cliente quanto o barbeiro têm a escolha de cancelar o horário agendado a qualquer momento. Para realizar o cancelamento o interessado entra no sistema, clica em sua agenda, escolhe o horário que deseja cancelar e clica em cancelar. O interessado receberá um aviso de conformação e depois de confirmado o horário fica livre para qualquer outro cliente. Não existe a função de reagendar (postergar ou adiantar) um atendimento, para reagendar um horário, o cliente deve cancelar o horário anterior e agendar um novo. Portanto, não existe a edição de um horário. AO cancelar um horário a outra parte interessada receberá um aviso de cancelamento. O horário cancelado permanecerá no histórico do cliente e do barbeiro com status cancelado.

* UCC#03: avaliar serviço - ref. RF#03

  Após o pagamento do serviço prestado (e somente após seu pagamento) o cliente poderá classificar a qualidade do serviço prestado pelo barbeiro através do mecanismo de estrelas. O mecanismo de pontuação vai de um a cinco estrelas (pontos), sendo zero a ideia de que não quer avaliar. A avaliação não é obrigatória e caso seja feita será de modo anônimo para o barbeiro. Para garantir a que o cliente continuará anônimo no processo de avaliação, a agregação das notas não é feita imediatamente após a avaliação do cliente e sim após 10 avaliações. Também a fim de manter o processo anônimo, não é permitido descrever a reclamação ou elogio.

* UCC#04: notificar agendamento - ref. RF#04

  Quando se aproximar do horário marcado o sistema alertará o usuário de que ele tem um horário agendado. Esse alerta é configurado no momento do agendamento (quanto tempo antes deseja ser avisado). O alerta se dará por notificação simples, pelo próprio aplicativo. O usuário pode escolher não ser avisado.

* UCC#05: verificar histórico - ref. RF#05

  Tanto o cliente quanto o barbeiro podem ver todos os agendamentos passados ou futuros. Nenhum agendamento poderá ser excluído (apenas cancelado) e todos aparecem nesta listagem. O interessado pode filtrar por status, serviço, barbeiro / cliente e data. O interessado também pode ordenar por esses mesmos campos. Nessa funcionalidade, juntamente com a listagem, o interessado pode cancelar o agendamento ou avaliar o serviço (caso já tenha pago por ele).

* UCC#06: salvar perfil - ref. RF#06

  Tanto o cliente quanto o barbeiro podem atualizar as informações no aplicativo que foram dadas no momento do cadastro. As informações de cadastro são: nome, telefone, e-mail e uma foto para o avatar. Destas, somente o avatar é opcional. Essas informações vêm da integração com o serviço de autenticação Oauth2 dos serviços terceiros (Twitter, Google e Facebook) ou são informadas manualmente. Caso o usuário tenha se cadastrado manualmente, a senha é enviada por e-mail a fim de conformar sua existência.

* UCC#07: plataforma - ref. RNF#01

  Para que o aplicativo funcione, tanto em IOS quanto em Android, este é desenvolvido em node.js e funções específicas são evitadas, a fim de manter a compatibilidade com ambas as plataformas.

* UCC#08: layout - ref. RNF#02

  Todo o layout do aplicativo deve seguir a identidade da barbearia, enviada por e-mail. Essas regras são de cabeçalho, ícones, imagens, fontes, rodapé.... Principalmente quanto a cores primárias e secundárias usadas.

* UCC#09: autenticar usuário - ref. RNF#03

  Todos os usuários do sistema devem ser autenticados e ter permissão de acesso ao conteúdo do sistema. Para tal, o sistema apresentará uma tela de login para que o usuário digita seu login e a senha (pelo menos 8 caracteres alfanumérico) ou escolher um provedor oauth2 (Google, Facebook ou Twitter). Nenhuma outra tela do sistema pode ser acessada sem que o usuário passe antes pela tela de login. Caso o usuário não tenha um login e senha no sistema ele deve clicar em "criar conta", preencher o formulário e então se autenticar com seu login e senha (ou provedor oauth2). Os campos a serem preenchidos são nome, telefone, e-mail e uma foto para o avatar e destes somente o avatar é opcional. Cada usuário poderá ter apenas um cadastro no sistema que será validado pelo e-mail cadastrado
