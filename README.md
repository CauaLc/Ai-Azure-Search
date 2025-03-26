# Azure AI Search - Configuração e Insights

## Introdução
Este repositório demonstra como configurar uma pesquisa inteligente utilizando a **Azure AI Search**, permitindo a extração eficiente de informações a partir de grandes conjuntos de dados.

## Pré-requisitos
- Conta no **Microsoft Azure**
- Um serviço **Azure AI Search** criado
- Chave e endpoint do serviço

## Configuração Passo a Passo

### 1. Instalar dependências
Instale o SDK da Azure para pesquisa de documentos:
```sh
pip install azure-search-documents
```

### 2. Configurar as credenciais
Defina as credenciais do serviço no seu código Python:
```python
from azure.search.documents import SearchClient
from azure.core.credentials import AzureKeyCredential

service_endpoint = "https://seu-endereco.search.windows.net"
index_name = "meu-indice"
api_key = "SUA_CHAVE_AQUI"

search_client = SearchClient(endpoint=service_endpoint, index_name=index_name, credential=AzureKeyCredential(api_key))
```

### 3. Inserir documentos no índice
Adicione documentos ao seu serviço de pesquisa:
```python
documents = [
    {"id": "1", "title": "Inteligência Artificial", "content": "IA está revolucionando o mundo."},
    {"id": "2", "title": "Aprendizado de Máquina", "content": "Machine Learning é uma subárea da IA."}
]

result = search_client.upload_documents(documents=documents)
print("Documentos inseridos:", result)
```

### 4. Executar uma pesquisa
Realize buscas nos documentos indexados:
```python
results = search_client.search(search_text="Inteligência")
for result in results:
    print(f"ID: {result['id']} - Título: {result['title']}")
```

## Insights
- **Facilidade**: A Azure AI Search simplifica a indexação e recuperação de dados.
- **Escalabilidade**: Suporte para grandes volumes de dados sem comprometer a performance.
- **Relevância**: Algoritmos da Azure ajudam a melhorar a precisão dos resultados da busca.

Agora seu projeto está pronto para ser apresentado! 🚀
