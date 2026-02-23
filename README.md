# Projeto de Matemática Computacional – Alocação de Enfermeiros (NRA)

Este repositório contém a implementação de um solucionador para o problema de alocação de enfermeiros a quartos por turno (*Nurse-to-Room Assignment* – NRA), utilizando Programação Linear Inteira (PLI) e um Algoritmo Genético (GA). O projeto foi desenvolvido como trabalho final da disciplina de Matemática Computacional, seguindo as diretrizes da competição IHTC‑2024.

## 📁 Estrutura do Repositório

- `Notebook/Codigos_para_o_artigo_Matemática_Computacional.ipynb` – Notebook principal com todo o código (upload de dados, PLI, GA, análise de sensibilidade e geração de tabelas).
- `README.md` – Este arquivo com instruções de uso.
- `convergencia_i04.png` - Grafico de convergencia para a instancia I04.
- `convergencia_i05.png` - Grafico de convergencia para a instancia I05.
- `convergencia_i06.png` - Grafico de convergencia para a instancia I06.
- `convergencia_i18.png` - Grafico de convergencia para a instancia I18.
- `tabela_comparacao_final.csv` – Tabela comparativa gerada após execução (será criada automaticamente).
- `tabela_sensibilidade_geral.csv` – Tabela de análise de sensibilidade (será criada automaticamente).

## 🚀 Como executar o código

### Pré‑requisitos

- Uma conta no Google (para utilizar o Colab).
- Navegador web atualizado.
- Arquivos de instância baixados do dataset oficial disponibilizado pelo professor.  
  Cada instância é composta por três arquivos obrigatórios:
  - `instance_info.json`
  - `nurse_shifts.csv`
  - `occupied_room_shifts.csv`

### Passo a passo

1. **Acesse o Google Colab**  
   Abra o link: [Google Colab](https://colab.research.google.com/) e faça o upload do notebook `Codigos_para_o_artigo_Matemática_Computacional.ipynb`.

2. **Execute o Bloco 1 – Upload dos dados**  
   - Ao executar a célula, será solicitado o nome da instância (ex: `i01`, `i04`, `i18`). Você deve digitar o nome da instãncia.  
   - Em seguida, aparecerá um botão para selecionar os três arquivos da instância. Selecione‑os todos de uma vez e aguarde o upload.  
   - Os arquivos serão salvos em uma pasta com o nome da instância dentro do ambiente do Colab.

3. **Execute o Bloco 2 – Resolvedor PLI**  
   Carrega a função de otimização exata. Nenhuma ação adicional é necessária.

4. **Execute o Bloco 3 – Algoritmo Genético**  
   Carrega as funções do GA. Nenhuma ação adicional é necessária.

5. **Execute o Bloco 4 – Execução PLI + GA**  
   - O PLI será executado com limite de 300 segundos (pode ser alterado no código se quiser).  
   - O GA será executado com 5 repetições, população 50, 100 gerações e taxa de mutação 0,1.  
   - Ao final, será exibido um gráfico de convergência e a tabela comparativa acumulada.  
   - A tabela é salva como `tabela_comparacao_final.csv` e o gráfico como `convergencia_<instancia>.png`.

6. **Execute o Bloco 5 – Análise de Sensibilidade**  
   - Para a instância atual, testa‑se o GA com populações de tamanho 20, 50 e 100.  
   - Os resultados são armazenados e exibidos em uma tabela acumulativa (`tabela_sensibilidade_geral.csv`).

7. **Repita para outras instâncias**  
   Para testar uma nova instância, volte ao Bloco 1 e informe outro nome. Os resultados serão acumulados nas tabelas.

## ⚙️ Personalização

- **Parâmetros do GA**: no Bloco 4, altere os valores de `pop_size`, `generations`, `mutation_rate` e `repetitions` diretamente na chamada da função `run_ga`.
- **Limite de tempo do PLI**: no Bloco 4, modifique o parâmetro `time_limit` da função `solve_pli`.
- **Análise de sensibilidade**: no Bloco 5, você pode alterar a lista `pop_sizes` para testar outros valores.

## 📊 Resultados esperados

- O PLI retorna o custo ótimo (quando factível) e o tempo de execução.
- O GA retorna o melhor custo, a média e o desvio padrão das 5 execuções, além do tempo médio.
- A análise de sensibilidade mostra o impacto do tamanho da população no desempenho do GA.

## 🧪 Instâncias recomendadas

Conforme o enunciado do projeto, as instâncias sugeridas são:

| Nível         | Instâncias | Finalidade                     |
|---------------|------------|--------------------------------|
| Teste         | i01, i02, i03 | Instâncias mínimas          |
| Recomendado   | i04, i06   | Comparação solver × meta      |
| Desafio       | i05, i18   | Apenas viável em meta          |

> **Nota**: Instâncias muito grandes podem exceder o tempo limite do PLI ou a memória disponível no Colab.

## 📝 Artigo

O arquivo `main.tex` (com o estilo `sbc-template.sty`) deve ser preenchido com os resultados obtidos. As tabelas e gráficos gerados podem ser inseridos diretamente no documento.

## 🧰 Dependências

Todas as bibliotecas necessárias são instaladas automaticamente na primeira célula do notebook:
- `pulp`
- `pandas`
- `matplotlib`
- `numpy`

## 📌 Observações

- O código foi desenvolvido para execução no Google Colab. Caso deseje executar localmente, ajuste os caminhos e remova as células específicas do Colab (como `files.upload()`).
- Certifique‑se de que os três arquivos da instância estejam nomeados exatamente como esperado: `instance_info.json`, `nurse_shifts.csv`, `occupied_room_shifts.csv`.
- Os resultados acumulados persistem durante a sessão do Colab. Reiniciar o ambiente apagará as variáveis; execute novamente os blocos para recarregar.

## 👥 Autores

- Gian Victor Gonçalves Figueredo – [gian.figueiredo@icen.ufpa.br]
- Kaleo Nabor Pimentel da Cunha – [kaleo.cunha@icen.ufpa.br]

## 📄 Licença

Este projeto é de cunho acadêmico e segue as diretrizes da disciplina. Uso livre para fins educacionais.
