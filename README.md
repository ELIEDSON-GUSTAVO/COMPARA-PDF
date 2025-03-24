# Comparador de PDFs de Pedidos de Caminhão

Este script Python permite comparar um novo PDF com PDFs antigos de pedidos de caminhões, buscando semelhanças em termos de dados como modelo, entre-eixo e carroceria. Ele usa técnicas de comparação de texto, como similaridade de cosine e comparação fuzzy, para encontrar PDFs que compartilham características semelhantes.

## Requisitos

- **Python 3.x**
- Bibliotecas:
  - `unicodedata`
  - `pdfplumber`
  - `os`
  - `re`
  - `sklearn` (para `TfidfVectorizer` e `cosine_similarity`)
  - `fuzzywuzzy` (para comparação de strings)
  - `tkinter` (para seleção de arquivos via interface gráfica)

Você pode instalar as dependências com o seguinte comando:

```bash
pip install pdfplumber scikit-learn fuzzywuzzy
Funcionalidade
O script realiza as seguintes operações:

Extração de Texto de PDF: O texto é extraído de arquivos PDF usando a biblioteca pdfplumber, incluindo o conteúdo de tabelas, caso existam.

Normalização de Texto: A função normalizar_texto remove acentos e coloca o texto em minúsculas para facilitar comparações.

Extração de Dados do Caminhão: O script busca informações específicas sobre o caminhão, como o modelo, entre-eixo e tipo de carroceria.

Cálculo de Similaridade: Utiliza o algoritmo TF-IDF e a similaridade de cosseno para calcular a similaridade entre textos extraídos dos PDFs.

Comparação de PDFs: O script compara o novo PDF selecionado com PDFs antigos de pedidos para encontrar os mais similares com base no modelo, entre-eixo e carroceria.

Passos de Comparação:
Selecionar o Novo PDF: Através de uma interface gráfica, você escolhe o novo PDF.

Comparação com PDFs Antigos: O script procura PDFs antigos na pasta especificada e calcula a similaridade.

Exibição dos Resultados: O script exibe os 6 PDFs mais semelhantes com base na similaridade estrutural, modelo, entre-eixo e carroceria.

Como Usar
Clone ou baixe o repositório.

Execute o script no Python:

bash
Copiar
Editar
python comparador_pdf.py
Ao executar, será solicitada a seleção de um novo PDF a ser comparado.

O script irá então comparar este PDF com os PDFs armazenados na pasta T:\1 - DOC PROJETOS\PD DE VENDA (ou qualquer pasta de sua escolha) e exibirá os resultados no terminal.

Exemplo de Resultado:
yaml
Copiar
Editar
📄 Comparando com o PDF: pedido_1234.pdf
🔍 Modelo Novo: Volvo FH16 | Modelo Antigo: Volvo FH16
🔍 Similaridade Estrutural: 85.50%
----------------------------------------
📋 Os 6 PDFs mais similares são:
1. pedido_1234.pdf - Similaridade da estrutura: 85.50%
2. pedido_5678.pdf - Similaridade da estrutura: 80.30%
...
Funções do Código
normalizar_texto(texto): Normaliza o texto removendo acentos e convertendo para minúsculas.

extrair_texto_pdf(pdf_path): Extrai o texto de um arquivo PDF.

extrair_dados_caminhao(texto): Extrai informações específicas do caminhão, como modelo, entre-eixo e carroceria.

extrair_itens_estrutura(texto): Extrai os itens de projetos da estrutura do caminhão.

calcular_similaridade(texto1, texto2): Calcula a similaridade entre dois textos usando o TF-IDF e a similaridade de cosseno.

comparar_com_pedidos_antigos(novo_pdf, diretorio_pdfs): Compara o novo PDF com PDFs antigos e exibe os resultados.

Observações
Certifique-se de que os PDFs antigos estão armazenados na pasta correta especificada no código.

O código pode ser facilmente adaptado para diferentes estruturas de PDF ou diretórios de arquivos.

Contribuições
Sinta-se à vontade para contribuir com melhorias ou correções neste projeto. Crie um fork deste repositório e envie um pull request.

Licença
Este projeto está sob a Licença MIT - consulte o arquivo LICENSE para mais detalhes.
