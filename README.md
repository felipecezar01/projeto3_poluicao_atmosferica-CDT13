# Projeto Final — Alerta Vermelho (Datathon Investigativo)

- **Disciplina:** Programação para Ciência de Dados
- **Curso:** MBA em Ciência de Dados — UNIFOR (Turma 13)
- **Professor:** Cássio Pinheiro
- **Equipe:** Felipe Cezar

---

## O Problema Investigado
A Secretaria de Meio Ambiente detectou um aumento alarmante de internações por doenças respiratórias em bairros específicos. O objetivo desta investigação foi cruzar três bases de dados isoladas (qualidade do ar, internações e cadastro de indústrias) para descobrir de onde vem a poluição, quando ela acontece e quem é o verdadeiro responsável pela crise de saúde pública.

## Principais Descobertas
- O fator climático (A Seca): Comprovamos que a época do "B-R-O Bró" agrava as internações, pois a falta de chuvas impede a lavagem da atmosfera, criando uma estufa de poluentes.
- A Cena do Crime (Jurema): A zona industrial da Jurema apresentou níveis de poluição até 4 vezes maiores que áreas residenciais, cravando um IQA de 199.3 (Alerta/Péssimo).
- O Relógio do Crime: As emissões não ocorrem em horário comercial. Os níveis de Material Particulado Grosso (MP10) e Dióxido de Enxofre (SO2) explodem mais de 76% acima da média exclusivamente às 22h e 00h.
- O Xeque-Mate: A empresa QuimNorte Ltda (Química Industrial) foi identificada como a fonte poluidora, operando com licença ambiental vencida desde 2021 e burlando a fiscalização ao concentrar a queima de compostos químicos na madrugada.

## Como Executar
1. Clone este repositório em sua máquina local.
2. Certifique-se de que os arquivos `.csv` originais estejam dentro da pasta `data/`.
3. Instale as dependências necessárias: `pip install pandas numpy matplotlib seaborn`
4. Abra e execute o arquivo `notebooks/investigacao.ipynb` célula por célula.

## Vídeo de Storytelling
- [Assista ao mini-documentário da investigação aqui] (INSERIR O LINK DO YOUTUBE/DRIVE AQUI)

## Estrutura do Repositório
- alerta-vermelho-CDT13/
  - README.md (Documentação principal)
  - notebooks/investigacao.ipynb (Notebook com a análise completa e storytelling)
  - data/ (Bases de dados em CSV)

## Tecnologias Utilizadas
- Python 3
- Pandas (Tratamento, merge e análise temporal)
- NumPy (Cálculo do Índice de Qualidade do Ar)
- Matplotlib e Seaborn (Visualização de dados e gráficos)