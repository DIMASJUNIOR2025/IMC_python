```markdown
# Calculadora de IMC com Widgets Interativos

Este notebook Colab demonstra o uso de `ipywidgets` para criar uma interface de usuário interativa para calcular o Índice de Massa Corporal (IMC) e fornecer informações sobre idade e altura.

## Funcionalidades

- **Entrada de Dados**: Permite ao usuário inserir seu nome, idade, peso e altura através de widgets interativos.
- **Cálculo de IMC**: Calcula o IMC com base no peso e altura fornecidos e classifica o resultado (Abaixo do peso, Peso normal, Sobrepeso, Obesidade).
- **Classificação de Idade**: Informa se a pessoa é maior ou menor de idade.
- **Classificação de Altura**: Classifica a altura como "Baixo(a)", "Mediano(a)" ou "Alto(a)".
- **Estilo Dark Mode**: A interface é estilizada com um tema dark mode para uma melhor experiência visual.

## Como Usar

1.  **Execute a célula de código**: Execute a célula que contém todo o código Python. Isso renderizará os widgets na saída da célula.
2.  **Insira seus dados**: Utilize os campos de texto e o slider para inserir seu nome, idade, peso (em kg) e altura (em metros).
3.  **Clique em "Calcular Resultados"**: Após inserir os dados, clique no botão "Calcular Resultados".
4.  **Visualize os Resultados**: Os resultados serão exibidos na área de saída abaixo do botão, incluindo o status de idade, classificação de altura, IMC e sua categoria correspondente.

## Widgets Utilizados

-   `widgets.Text`: Para entrada do nome.
-   `widgets.IntSlider`: Para seleção da idade.
-   `widgets.FloatText`: Para entrada do peso e altura.
-   `widgets.Button`: Para acionar o cálculo dos resultados.
-   `widgets.Output`: Para exibir os resultados e mensagens de erro.
-   `widgets.VBox`: Para organizar os widgets verticalmente.

## Estilização

Um bloco de estilo CSS personalizado é injetado no notebook para aplicar um tema "Dark Mode" aos widgets e ao contêiner principal, proporcionando uma aparência moderna e agradável.

## Código

O código Python define as funções para processar os dados inseridos, calcular o IMC e classificar a altura e a idade. Ele também configura os widgets e gerencia a interação com o usuário.


