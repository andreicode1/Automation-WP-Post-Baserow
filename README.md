Automação de Postagens no WordPress com n8n, HTML e Baserow

Recentemente, desenvolvi uma automação no n8n com o objetivo de facilitar e agilizar a publicação de conteúdos no WordPress. A solução integra diversas ferramentas e tecnologias de forma eficiente, permitindo que postagens sejam geradas automaticamente com base em dados estruturados.

Estrutura da Automação
A automação funciona em etapas sequenciais, envolvendo os seguintes componentes:

1. Geração de Título com OpenAI
Tudo começa com a geração de um título de postagem por meio da OpenAI, que é responsável por criar sugestões criativas e relevantes com base em determinados parâmetros. Esse título é enviado automaticamente para uma base de dados no Baserow utilizando o método create do n8n.

2. Banco de Dados com Baserow
O Baserow funciona como o banco de dados central do projeto. Ele armazena os títulos gerados, além de outros campos necessários para o controle do fluxo de publicação, como:

Campo de título

Campo de conteúdo formatado em HTML

Campo tipo checkbox para indicar se a postagem já foi publicada

3. Consulta e Atualização com GET e UPDATE
Com o método get, o n8n realiza uma consulta no Baserow para verificar o status de cada item. Caso o campo checkbox esteja marcado como false, o fluxo continua e é feita a publicação automática no WordPress, utilizando uma requisição com o conteúdo formatado em HTML.

Após a publicação, o n8n utiliza o método update para alterar o valor do checkbox para true, evitando que o mesmo conteúdo seja postado novamente.

Por outro lado, se o checkbox estiver marcado como true, o sistema interpreta que aquela entrada já foi publicada e procede com a criação de uma nova postagem, reiniciando o fluxo com um novo título.

Benefícios da Automação
Redução de tempo gasto com postagens manuais

Consistência na formatação, graças ao uso de HTML

Controle total do processo através do Baserow

Evita duplicações com a lógica condicional de verificação

Essa automação tornou o processo de publicação muito mais dinâmico, abrindo espaço para escalar a produção de conteúdo com mais qualidade e menos esforço manual.

![image](https://github.com/user-attachments/assets/4debdd4a-da36-435d-894a-cbc5aee02b2c)
