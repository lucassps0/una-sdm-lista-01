# una-sdm-lista-01
Centro Universitário UNA
Sistemas Distribuídos e Mobile
Professor Daniel Henrique Matos de Paiva
Lista de Exercícios I

Exercícios:

Atividade: Operação Rastreio e Logística
Contexto: Vocês são desenvolvedores de uma nova startup de entregas, a
"DistribuídaLog". Um cliente internacional quer enviar uma encomenda para o
Brasil, mas ele só tem o número do CEP. Sua missão é validar se esse CEP
existe e extrair os dados para o formulário de entrega usando o Postman (ou
Bruno/Insomnia).
Passo 1: A Investigação (O Endereço do Servidor)
Para conversar com um Sistema Distribuído, primeiro precisamos saber o seu
endereço (Endpoint).
O ViaCEP atende no endereço: https://viacep.com.br/ws/{CEP}/json/

Passo 2: Mão na Massa (Requisições)
Abra o seu cliente HTTP (Postman/Bruno) e realize as seguintes tarefas:
1. A Entrega Padrão:
o Crie uma requisição do tipo GET.
o Tente buscar o CEP da nossa faculdade (ou um famoso, como o
da Sé em SP: 01001000).
o Pergunta: Qual foi o Status Code retornado? O JSON veio
completo?

2. O Caso do CEP Inexistente:
o Tente fazer um GET para um CEP que não existe (ex: 99999999).
o Desafio: Observe o JSON retornado. O ViaCEP retorna um erro 404
ou ele retorna um JSON com um campo "erro": true? Por que você
acha que eles escolheram essa estratégia?

3. Mudando o Formato (O Camaleão):
o O ViaCEP é incrível porque ele aceita outros formatos além do
JSON. Tente mudar o final da URL de /json/ para /xml/.
o Pergunta: O que mudou na visualização dos dados? Qual formato
parece mais fácil de ler no C#?

Passo 3: O Relatório do Engenheiro
Após realizar os testes, responda:
1. Verbo HTTP: Qual método você usou? Por que não usamos POST para
consultar um CEP?
2. Análise de Dados: Copie o JSON do seu CEP e identifique:
o Qual é a Chave (Key) que guarda o nome da cidade?
o Qual é a Chave que guarda o nome da rua?

3. Integração C#: Se você fosse criar uma classe em C# para receber
esses dados, como ficaria a sua propriedade para a chave localidade?
Use o que aprendemos sobre [JsonPropertyName].
