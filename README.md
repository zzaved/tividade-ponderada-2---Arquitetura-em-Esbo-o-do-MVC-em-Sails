# Atividade ponderada - Arquitetura do MVC em Sails

<div align="center">
<sup>Figura 1 - Arquitetura em MVP da plataforma<sup>
<br>
<img src="mvcSails.png">
<sup>Fonte: Material produzido pelo grupo Tripulação Voluntária (2024)</sup>
</div>

## Sobre o projeto
• Nome do Projeto: Oportuniza - Plataforma de um mar de oportunidades do voluntariado
<br>
• Descrição: A plataforma Oportuniza busca conectar voluntários de todo o Brasil em uma rede de oportunidades ligadas aos serviços sociais e também fazer com que eles possam conhecer mais voluntários, formando assim uma rede de apoio.
<br>
• Arquitetura: MVC (Model-View-Controller)
<br>
• Ferramenta de Diagramação: draw.io
<br>

## Modelos (Models):
• User
<br>
    Atributos:
    <br>
    ID (ID Gerado para o usuário a partir do número de login)
    <br>
    Nome: Armazenar o nome do usuário
    <br>
    E-mail: Armazenar o e-mail do usuário
    <br>
    Senha: Armazenar a senha do usuário
    <br>
    Idade: Armazenar a idade do usuário para uma experiência personalizada
    <br>
    Local: Armazenar a localização do usuário para uma experiência personalizada
    <br>
    Gênero: Armazenar o gênero do usuário
    <br>
    Pontos: Índice que irá armazenar qual a pontuação do usuário a partir do seu número de engajamento com serviços voluntários para uma experiência de gamificação
    <br>
    Customização: Índice que irá armazenar como o mascote Otto daquele usuário estará personalizado (A plataforma Oportuniza disponibiliza que o carangueijo mascote tenha várias skins a partir da pontuação do usuário)
    <br>
• Post
<br>
    ID: índice para localizar a postagem daquele usuário
    <br>
    Título: Títutlo daquela postagem
    <br>
    Conteúdo: Corpo do texto daquela postagem
    <br>
    Anexos: Caso contenha, irá anexar arquivos ou imagens que estão presentes naquela postagem
    <br>
    UserID: ID do usuário que fez aquela postagem para fins de localização
    <br>
• Post
    <br>
    UserID: ID daquele usuário para que seja possível localizar o perfil
    <br>
    Descrição: Biografia do usuário
        <br>
    Interesse: Campos assinalados com as áreas de interesse daquele usuário
        <br>
    Carga horária: Fácil visualização da carga horária daquele usuário
        <br>

Todos esses itens são necessários para uma boa dinâmica da plataforma e funcionam entre si por necessitarem principalmente de um ID de usuário para atribuir funções e relacionar atividades. 

<br>
## Controladores (Controllers):
• Login do Usuário, tendo como responsabilidades "Verificar" (para verificar se aquele sistema de login já existe, e se sim, logar na conta) e "Cadastrar" (para usuários que não estão cadastrados ainda) um usuário específico na nossa plataforma. Esse controlador é ligado a View "Login", e para interagir com o Model chamado "User" irá criar um ID específico para aquele usuário e precisará receber como atributo nome, e-mail, senha, idade, local, gênero, e irá gerar uma pontuação e um ponto de customização para aquele usuário, já que a nossa plataforma terá uma dinâmica de personalizar um carangueijo.
<br>

• Publicações, tendo como responsabilidades "Criar" (para publicar algo), "Apresentar" (para exibir a publicação inteira) e "Deletar" (para excluir uma publicação específica). Esse controlador é ligado a View "Publicações", e para interagir com o model "Post" será criado um ID da publicação, e ela irá conter Título, o corpo do texto, também intitulado de "Conteúdo", Anexos, caso seja necessário para o usuário, e o próprio UserID para o sistema identificar a quem aquela publicação está ligada.
<br>

• Perfil, tendo como responsabilidades "Apresentar" (para exibir o perfil) e "Atualizar" (para atualizar algum ponto específico daquele perfil de usuário). Esse controlador é ligado a View "Perfil", e para interagir com o model "preferences" será enviado o UserID, uma descrição que está presente no perfil daquele usuário, os seus pontos de interesses para prestação de um trabalho voluntário e a sua carga horária total.
<br>

## Views (Views):
• Login: responsável pelo sistema de Login ou cadastro de um usuário
<br>
• Publicações: Responsável pelas postagens dos usuários que estarão presentes ao longo da plataforma
<br>
• Perfil: Responsável pela apresentação do perfil do usuário e as suas informações
<br>

## Infraestrutura:
• O Banco de dados utilizado é o PostgreSQL, so tipo SQL, e ele irá interagir com o projeto ao armazenar as diversas variáveis que estão presentes em Model, como informações a respeito dos usuários e informações a respeito de publicações.
<br>

## Implicações da Arquitetura:
Essa arquitetura faz com que o projeto do grupo tenha um índice de escalabiliade no sentido de que é fácil expandir para novos horizontes e novos projetos ao não armazenarmos dados que sejam específicos e que não são utilizados por outras plataformas. Para manutenção, podemos testar e analisar quais são as variáveis que estão apresentando algum problema de armazenamento e até se notarmos que ela não possui uma relevância significativa no projeto, a excluir pode ser algo viável a ser discutido entre o grupo. A Testagem fica por conta de verificar se realmente todas as variáveis presentes estarão desempenhando um papel útil de armazenamento. Com isso, concluimos que a arquitetura do sistema Oportuniza, do grupo Tripulação Voluntária é eficiente e tem uma enorme perspectiva de expansão.
<br>

## Aluno: Pablo de Azevedo - T11
