# ASM Identity Provider
Implementation of an OpenID connect provider to authenticates and authorizes identities with spring boot and spring security.

### Problema

Atualmente, nos aplicativos, o processo de autenticação usuários é descentralizado. Onde cada sistema tem a responsabilidade de implementar o controle de autenticação das identidades.

Nesse primeiro momento, autenticaremos o X como identity. 

### Solução

Criar um MS Identity Provider que implementará o contexto de segurança oferecendo uma estrutura de autenticação e autorização das identidades através de um fluxo de acordo com o protocolo OAuth 2.0.

## OAuth2

OAuth 2.0 permite um terceiro aplicativo para obter acesso limitado a um serviço HTTP, seja em nome de um proprietário de recurso orquestrando uma interação de aprovação entre o proprietário do recurso e o serviço HTTP, ou permitindo o aplicativo de terceiros para obter acesso em seu nome.

Abaixo, temos os players envolvidos no fluxo:

<img width="630" alt="oauth-2-players" src="https://user-images.githubusercontent.com/16579964/130367165-daf6015c-8427-4e70-971e-1f2691b9a714.PNG">

- O **Authorization Server** é a plataforma de identidade da Microsoft e é responsável por garantir a identidade do usuário, conceder e revogar acesso a recursos e emitir tokens. O servidor de autorização também é conhecido como **Identity Provider**. Ele lida com segurança com qualquer coisa relacionada às informações do usuário, seu acesso e as relações de confiança entre as partes em um fluxo.
- O **Resource Owner** é normalmente o usuário final. É a parte que possui os dados e tem o poder de permitir que os clientes acessem esses dados ou recursos.
- O **Client Application** é o aplicativo, identificado por ID de aplicativo. O **Client Application** geralmente é a parte com a qual o usuário final interage e solicita tokens do servidor de autorização. O cliente deve ter permissão para acessar o recurso pelo proprietário do recurso.
- O **Protected Resource** é onde o recurso ou dados residem. Ele confia no **Identity Provider** para autenticar e autorizar com segurança o cliente OAuth 2.0 e usa tokens de acesso do portador para garantir que o acesso a um recurso possa ser concedido.

Abaixo, temos um diagrama que expressa o o fluxo padrão de comunicação no protocolo OAuth 2.0 e OIDC:

<img width="821" alt="protocol-endpoints-in-use" src="https://user-images.githubusercontent.com/16579964/130366987-9533fcbf-270b-4cef-9bc0-7d585b82da34.PNG">
