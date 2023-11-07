# Módulo Cep

O Módulo Cep é uma extensão que permite obter informações de endereço com base em um CEP (Código de Endereçamento Postal) fornecido como parâmetro. O módulo retorna os detalhes do endereço em formato JSON.

## Como Utilizar

Siga os passos a seguir para integrar e utilizar o Módulo Cep em sua aplicação:

### Instalação

1. Instale o Módulo Cep em sua aplicação.

### Configuração

2. Selecione o formulário em que deseja usar o Módulo Cep.

3. Escolha o campo que será responsável por ativar o módulo.

4. Na aba "Extensão", selecione o módulo Cep.

### Procedimento

5. Acesse a aba "Procedimento" em que a codificação é realizada em T-SQL.

6. Para acessar o objeto de retorno do Módulo Cep, atribua o valor à variável de sistema `@@MODULE`. Por exemplo:

   ```sql
   DECLARE @EXTENSAO NVARCHAR(MAX) = @@MODULE

   SELECT 
       JSON_VALUE(@EXTENSAO, '$.logradouro') AS LOGRADOURO,
       JSON_VALUE(@EXTENSAO, '$.complemento') AS COMPLEMENTO,
       JSON_VALUE(@EXTENSAO, '$.bairro') AS BAIRRO,
       JSON_VALUE(@EXTENSAO, '$.cidade') AS CIDADE,
       JSON_VALUE(@EXTENSAO, '$.uf') AS UF


O código acima acessa o objeto de retorno com base no valor inserido no campo selecionado e retorna os valores. Cada alias preenche o campo do formulário correspondente.

### Exemplo de Utilização

Suponha que você tenha um campo chamado cep em seu formulário. Quando um CEP válido for inserido nesse campo e a extensão do Módulo Cep for ativada, o procedimento SQL acima será executado, preenchendo os campos do formulário com os detalhes do endereço.

Certifique-se de substituir os campos e alias conforme necessário para corresponder à estrutura do seu formulário.

Aproveite os benefícios do Módulo Cep para simplificar a obtenção de informações de endereço com base em CEPs.
