

Este projeto contém um sistema interativo em Python para coletar informações de usuários, classificar altura e calcular o Índice de Massa Corporal (IMC).

## 🚀 Funcionalidades

1.  **Entrada de Dados**: Coleta de nome, idade, peso e altura.
2.  **Lógica de Negócio**:
    *   Verificação de maioridade (18 anos).
    *   Classificação de estatura (Baixo, Mediano, Alto).
    *   Cálculo de IMC com classificação baseada nos padrões da OMS.
3.  **Interface Gráfica (GUI)**: Interface moderna utilizando `ipywidgets` com suporte a temas e estilização CSS personalizada.

## 🛠️ Tecnologias Utilizadas

*   **Python 3**
*   **ipywidgets**: Para a criação dos componentes de interface.
*   **IPython Display**: Para renderização de HTML/CSS.

## 📋 Como Usar

1. Execute o código no Google Colab.
2. Preencha os campos de Nome, Peso e Altura.
3. Utilize o slider para definir a Idade.
4. Clique em **Calcular Resultados** para gerar o relatório.
5. Use o botão **Limpar Campos** para resetar o formulário.
"""

with open('README.md', 'w', encoding='utf-8') as f:
    f.write(readme_content)

print("Arquivo README.md criado/atualizado com sucesso!")
