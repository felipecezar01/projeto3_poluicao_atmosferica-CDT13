# 🚨 Poluição Atmosférica
### Projeto 03 — Alerta Vermelho: Crise Ambiental Misteriosa

**Equipe:** Felipe Cezar

---

## 📋 Descrição da Operação
A Secretaria do Meio Ambiente detectou um aumento alarmante de internações por doenças respiratórias em bairros específicos da cidade. Embora as estações de monitoramento de qualidade do ar registrem dados há dois anos, esses registros nunca haviam sido cruzados com os dados hospitalares. 

O objetivo desta investigação é atuar como Cientista de Dados para conectar os pontos e descobrir: **de onde vem a poluição, quando ela acontece e quem está sendo afetado.**

---

## 🔍 Principais Descobertas
A investigação cruzou os bancos de dados de saúde e meio ambiente, revelando um padrão claro de crime ambiental:

* **As Vítimas:** Os bairros com os maiores índices de internações por doenças respiratórias são Maraponga, Jurema e Messejana.
* **A Sazonalidade:** Existem picos claros de internações que ocorrem entre julho e dezembro de cada ano. Este período coincide com a época de seca, facilitando a dispersão de partículas nocivas na atmosfera.
* **O Epicentro:** A Jurema apresentou níveis de poluição extremos. Somando a poluição de bairros afetados como Maraponga e Messejana, o valor ainda é inferior à carga poluidora concentrada apenas na Jurema.
* **A Assinatura do Crime:** A análise horária revelou que a poluição não é constante. Existem picos absurdos de emissão durante a madrugada (especialmente às 22h e 00h), indicando uma possível liberação intencional "às escondidas".
* **O Culpado:** O principal componente liberado nessas madrugadas é o SO2 (Dióxido de Enxofre), típico de indústrias químicas. O cruzamento com o banco de empresas revelou que a **Quim Norte LTDA**, uma indústria química localizada na Jurema, está operando com a licença ambiental vencida.

---

## ⚠️ Considerações e Limitações do Cenário (Adendos)
É importante ressaltar que este projeto opera sob um cenário parcialmente fictício e controlado. Em uma aplicação 100% real, a investigação exigiria mais rigor geográfico e demográfico:
1. **Anomalia Geográfica:** O dataset trata a "Jurema" como um bairro de Fortaleza. Na realidade, Jurema é um vasto distrito do município vizinho de Caucaia, englobando diversos bairros. 
2. **Dados Faltantes:** Uma análise real exigiria dados de densidade populacional (para calcular taxas de incidência proporcionais), variáveis meteorológicas (direção dos ventos) e um mapeamento completo de todas as empresas e hospitais da região metropolitana.

---

## 🛠️ Tecnologias Utilizadas
A investigação foi conduzida utilizando o ecossistema de dados da linguagem Python:
* **Linguagem:** Python 3
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização de Dados:** Matplotlib, Seaborn
* **Inteligência Geográfica:** Folium (com manipulação de arquivos GeoJSON)
* **Ambiente:** Jupyter Notebook

---

## 🚀 Como Executar
O projeto foi desenvolvido para ser de fácil reprodução. Para testar a investigação:
1. Abra o arquivo `notebooks/investigacao.ipynb` em um ambiente Jupyter ou no VS Code.
2. Certifique-se de ter as bibliotecas acima instaladas no seu ambiente virtual.
3. No menu superior, clique em **"Run All"** (Executar Tudo). O script rodará em cascata de cima a baixo, carregando os dados, realizando a limpeza e plotando os gráficos automaticamente.

---

## 📂 Estrutura do Repositório

```text
📦 projeto3_poluicao_atmosferica
 ┣ 📂 data/        # Bases de dados fornecidas (CSVs) e a malha territorial (GeoJSON) para validação geográfica.
 ┣ 📂 docs/        # Contém o Cartoon de apresentação da investigação.
 ┣ 📂 images/      # Arquivos HTML dos mapas interativos gerados durante a análise.
 ┣ 📂 notebooks/   
 ┃ ┗ 📜 investigacao.ipynb  # O "Diário de Investigação". Contém todo o fluxo de pensamento, tentativas, limpezas e validação de hipóteses.
 ┗ 📜 README.md
```
*Nota sobre o Notebook:* O arquivo `investigacao.ipynb` reflete o processo real de um Cientista de Dados iniciante resolvendo um problema do zero. Ele contém importações, tratamentos, validações de hipóteses (algumas corretas, outras descartadas) e o fluxo completo de raciocínio, priorizando o entendimento da investigação em detrimento de uma estruturação de software rígida.

---

## 🎬 O Cartoon (Substituição do Vídeo)
Devido à complexidade do documento e das ramificações da análise, o vídeo gerado automaticamente por IA (NotebookLM) não apresentou a precisão e a estrutura necessárias para contar essa história. 

Como alternativa para apresentar os achados de forma didática, visual e estruturada, desenvolvi um **Cartoon Investigativo** resumindo o caso (desconsiderando a parte técnica de tratamento de dados):

<div align="center">
  <img src="docs/cartoon.svg" alt="Cartoon da Investigação" width="100%">
</div>