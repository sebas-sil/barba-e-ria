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

<details>
  <summary>## Preparação para a reunião #3 (parte 2/3) - cenários de uso - 2020-mar-28</summary>

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
</details>

<details>
  <summary>## Preparação para a reunião #3 (parte 3/3) - caso de uso - 2020-abr-04</summary>

Com a descrição dos casos de cada requisito em cenários de caso de uso, estou pronto para desenhar os casos de uso do sistema. Primeiro criei o diagrama de caso de uso e depois descrevi cada caso de uso do diagrama.

<img src="engenharia/Diagrama de caso de uso completo.png" title="Diagrama de caso de uso completo"/>

| UC#01 | Autenticar usuário |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condições       | O usuário deve ter acesso ao sistema |
| Objetivo | Autenticar e autorizar o usuário |
| pos-condições | O usuário estará autenticado |
| Origem | UCC#09 |
| Fluxo principal |  |
|  | <ol><li>O sistema apresenta a tela de autenticação. </li><li>O usuário informa seu login e senha. </li><li>O usuário clica em "autenticar". </li><li>O sistema redireciona para a funcionalidade requisitada ou a tela de boas vindas</li></ol> |
| Fluxo alternativo #1 | Usuário não tem cadastro (cadastro manual) |
|  | <ol><li>O usuário clica em "cadastrar". </li><li>O usuário preenche o formulário de cadastro. </li><li>O sistema valida as informações. </li><li>O sistema envia a senha do usuário para o e-mail informado. </li><li>O sistema envia o usuário para o passo 1 do fluxo principal. </li><ol> |
| Fluxo alternativo #2 | Usuário com login ou senha incorretos |
|  | <ol><li>O sistema envia o usuário para o passo 1 do fluxo principal. </li><li>O sistema apresenta a mensagem de erro "usuário ou senha inválidos"</li><ol> |
| Fluxo alternativo #3 | Autenticação Oauth2 |
|  | <ol><li>O usuário escolhe autenticar-se por uma provedor externo clicando em um dos botões Oauth2 disponíveis. </li><li>O sistema se comunica com o provedor e valida as informações recebidas. </li><li>O sistema encaminha o usuário para o passo 4 do fluxo principal</li></ol> |
| Fluxo alternativo #4 | Usuário já existe |
|  | <ol><li>O sistema valida que o e-mail informado já existe. </li><li>O sistema permanece da tela de cadastro. </li><li>O sistema apresenta o erro de "usuário já cadastrado". </li></ol> |
  
| UC#02 | Marcar horário |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condições | <ul> <li>O cliente deve estar autenticado</li> <li>Devem existir serviços cadastrados</li> <li>Devem existir barbeiros cadastrados</li> </ul> |
| objetivo | Agendar um serviço com o barbeiro em um determinado horário |
| pos-condições | Agendamento realizado com sucesso e aparecendo no histórico |
| Origem | UCC#01 |
| Fluxo principal |  |
|  | <ol> <li>O sistema apresenta a tela de agendamento.</li> <li>O usuário escolhe um serviço.</li> <li>O usuário escolhe um barbeiro.</li> <li>O sistema apresenta a agenda do barbeiro com os horários livres.</li> <li>O usuário escolhe uma janela livre.</li> <li>O usuário clica em "agendar horário".</li> <li>O sistema valida as informações.</li> <li>O sistema apresenta a tela de boas vindas.</li> <li>O sistema mostra a mensagem de "agendamento realizado com sucesso".</li> </ol> |
| Fluxo alternativo #2 | Janela ocupada |
|  | <ol> <li>O sistema verifica que a janela escolhida não esta livre.<li> <li>O sistema permanece na tela de agendamento.</li> <li>O sistema marca a janela escolhida como "ocupada".</li> <li>O sistema mostra a mensagem de "O horário escolhido não esta livre.".</li> <li>O sistema encaminha o usuário para o passo 5 do fluxo principal.</li>  </ol> |

| UC#3 | Cancelar agendamento |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condição | <ul> <li>O cliente deve estar autenticado</li> <li>Devem existir agendamentos cadastrados</li> </ul> |
| objetivo | Cancelar um agendamento previamente realizado |
| pos-condições | O agendamento aparece como "cancelado" no histórico |
| Origem | UCC#02 |
| Fluxo principal | <ol> <li>O usuário clica em "ver histórico".</li> <li>O sistema apresenta a tela de histórico.</li> <li>O usuário clica em "cancelar agendamento" no item que deseja cancelar.</li> <li>O sistema cancela o agendamento.</li> <li>O sistema permanece na tela de histórico.</li> <li>O sistema marca o agendamento escolhido como "cancelado".</li>  </ol> |
| Fluxo alternativo #1 | O agendamento não pode ser cancelado |
|  | <ol> <li>O sistema permanece na tela de histórico de agendamento.</li> <li>O sistema mostra a mensagem "Não foi possível cancelar o agendamento" e o motivo da impossibilidade.</li> <li>O sistema encaminha o usuário para o passo 3 do fluxo principal.</li>  </ol> |

| UC #4 | Avaliar serviço |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condição | <ul> <li>O usuário deve estar autenticado</li> <li>O serviço já estar concluído (pago)</li>  </ul> |
| objetivo | Avaliar o serviço prestado pelo barbeiro |
| pos-condições | Agendamento é mostrado no histórico já com a avaliação |
| Origem | UCC#03 |
| Fluxo principal |  |
|  | <ol> <li>O cliente clica em "ver histórico".</li> <li>O sistema apresenta a tela de histórico.</li> <li>O cliente clica em "avaliar serviço" no item que deseja avaliar.</li> <li>O sistema apresenta a tela de avaliação.</li> <li>O cliente clica na quantidade de estrelas que deseja dar ao serviço.</li> <li>O cliente clica em "finalizar".</li> <li>O sistema apresenta a tela de histórico.</li> <li>O sistema marca o agendamento como avaliado (com a nota).</li>  </ol> |
| Fluxo alternativo #1 | O serviço não pode ser avaliado |
|  | <ol> <li>O sistema apresenta a tela de histórico.</li> <li>O sistema mostra a mensagem "Não foi possível avaliar o serviço" e o motivo da impossibilidade.  <li>O sistema encaminha o cliente para o passo 3 do fluxo principal.</li> </ol> |

| UC#5 | Verificar histórico |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condição | <ul> <li>O usuário deve estar autenticado.</li>  </ul> |
| objetivo | Listar os agendamentos do cliente ou do barbeiro |
| pos-condição | Lista dos agendamentos |
| Origem | UCC#05 |
| Fluxo principal |  |
|  | <ol> <li>O cliente clica em "ver histórico".</li> <li>O sistema apresenta a tela de histórico.</li> <li>O sistema lista os agendamentos por ordem que serão executados (mais recente).</li>  </ol> |
| Fluxo alternativo #1 | Não existem agendamentos |
|  | <ol> <li>O sistema apresenta a tela de agendamentos.</li> <li>O sistema mostra a mensagem "Não existem agendamentos".</li> <li>O sistema permanece na tela de histórico.</li> </ol> |
| Fluxo alternativo #2 | Filtro apicado |
|  | <ol> <li>O usuário escolhe um filtro para aplicar a lista.</li> <li>O sistema aplica o filtro escolhido.</li> <li>O sistema encaminha o usuário para o passo 3 do fluxo principal.</li>  </ol> |
| Fluxo alternativo #3 | Ordem aplicada |
|  | <ol> <li>O usuário escolhe uma ordenação para aplicar a lista.</li> <li>O sistema aplica a ordenação escolhido.</li> <li>O sistema encaminha o usuário para o passo 3 do fluxo principal.</li> </ol> |

| UC #6 | Atualizar perfil |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pre-condição | O usuário deve estar autenticado. |
| objetivo | Atualizar as informações de cadastro do usuário |
| pos-condição | Informações atualizadas |
| Origem | UCC#06 |
| Fluxo principal |  |
|  | <ol> <li>O usuário clica no seu avatar.</li> <li>O sistema apresenta a tela de cadastro para o usuário.</li> <li>O usuário clica no campo que deseja alterar.</li> <li>O usuário insere a nova informação.</li> <li>O usuário clica em salvar".</li> <li>O sistema valida e salva as informações.</li> <li>O sistema permanece na tela de cadastro.</li>  </ol> |
| Fluxo alternativo #1 | Campo obrigatório não informado |
|  | <ol> <li>O sistema mostra a mensagem de "campo não informado" e o nome do campo.</li> <li>O sistema permanece na tela de cadastro.</li>  </ol> |
| Fluxo alternativo #2 | Usuário informa e-mail já existente |
|  | <ol> <li>O sistema mostra a mensagem de "e-mail já cadastrado". <li>O sistema permanece na tela de cadastro.</li> </ol> |
</details>

## Preparação para a reunião #3 (parte 3/3) - diagrama de classes - 2020-abr-11
Depois de descrito os casos de uso, o entendimento está melhor sobre o que o sistema deve fazer e do que precisamos para fazer. Assim, desenhamos o primeiro esboço do diagrama de classes. Não é necessário se preocupar com assertividade neste momento, apenas passe para o papel o que ja tem.

<p align="center">
  <img src="engenharia/Diagrama de classes.png" title="Diagrama de classes uso completo"/>
</p>
Como pode ser visto, o diagrama não tem tipos (exceto a generalização) nem cardinalidade. Apenas removemos de nossas mentes e materializamos.
