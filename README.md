# Challenge-Telecom-X
Desafio Telecom X - Aplicação prática do conhecimento - especialização Data Science Oracle | Alura

📊 Projeto: Análise e Previsão de Evasão de Clientes (Churn)
Este projeto tem como objetivo preparar um conjunto de dados para análise preditiva de evasão de clientes (churn), aplicando técnicas de limpeza, padronização e transformação de dados para uso em algoritmos de machine learning.

🧹 Etapas de Limpeza e Transformação

✅ 1. Padronização de texto
Todos os valores textuais (object) foram convertidos para minúsculas e tiveram espaços em branco removidos.

Exceções: colunas customerID e Churn foram preservadas inicialmente para validações específicas.

✅ 2. Correções de inconsistências
Valores como 'no internet service' e 'no phone service' foram padronizados para 'no', a fim de evitar ambiguidade e facilitar conversão posterior para booleanos.

Verificou-se a consistência entre colunas como internet.InternetService e colunas dependentes (ex.: internet.OnlineSecurity).

✅ 3. Tratamento de valores nulos e inválidos
Coluna account.Charges.Total continha strings vazias (''), que foram convertidas para NaN, e posteriormente preenchidas com 0.0.

Foi aplicada a função pd.to_numeric(..., errors='coerce') para garantir conversão segura de tipos.

✅ 4. Remoção de registros inválidos
Registros com Churn igual a string vazia ('') foram removidos do dataset, pois não representavam informação útil para o modelo preditivo.

✅ 5. Conversões de tipo
Valores 'yes' e 'no' foram mapeados para 1 e 0 respectivamente, mantendo compatibilidade com modelos de machine learning.

Campos booleanos foram convertidos para int para uso direto em modelos.

✅ 6. Renomeação de colunas
Colunas foram renomeadas com nomes mais descritivos e em português, mantendo os prefixos originais (customer., phone., internet., account.).

Exemplo:

customer.gender → Gênero do cliente

account.Charges.Total → Valor Total

internet.StreamingTV → Streaming TV


🧠 Objetivo
Após a limpeza, o conjunto de dados está pronto para:

Análise exploratória (EDA)

Treinamento de modelos preditivos (classificação binária)

Interpretação de variáveis associadas à evasão de clientes


🗃️ Backup dos dados
Os dados foram salvos em formato .json para fins de versionamento e auditoria.

python
Copy
Edit
df.to_json('backup_dados.json', orient='records', lines=True, force_ascii=False)



Este desafio foi pensado para aplicar os conhecimentos adquiridos nos seguintes formações:

🛠️ Bibliotecas utilizadas
* NumPy: análise numérica eficiente com Python
* Pandas: conhecendo a biblioteca
* Pandas I/O: trabalhando com diferentes formatos de arquivos
* Pandas: transformação e manipulação de dados
* Data Visualization: matplotlib / seaborn (opcional para EDA) - criando gráficos com bibliotecas Python
