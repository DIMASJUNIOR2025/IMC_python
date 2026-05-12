# 🏋️ Calculadora de IMC — Google Colab / Jupyter Notebook

> Aplicação interativa de cálculo de Índice de Massa Corporal (IMC) com interface visual estilo *dark mode*, construída com `ipywidgets` para uso em ambientes Colab e Jupyter.

---

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Pré-requisitos](#pré-requisitos)
- [Como Usar](#como-usar)
- [Estrutura do Código](#estrutura-do-código)
- [Lógica de Classificação](#lógica-de-classificação)
- [Interface](#interface)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Possíveis Melhorias](#possíveis-melhorias)
- [Licença](#licença)

---

## 📌 Sobre o Projeto

Este projeto implementa uma calculadora de **IMC (Índice de Massa Corporal)** interativa diretamente em células de notebook, sem necessidade de backend ou servidor externo. A interface é construída com **ipywidgets** e estilizada com CSS injetado via `IPython.display.HTML`, proporcionando uma experiência de usuário fluida com tema escuro.

O notebook foi desenvolvido originalmente no **Google Colab** e é compatível com qualquer ambiente **Jupyter Notebook / JupyterLab**.

---

## ✅ Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| 📝 Entrada de nome | Campo de texto para identificação do usuário |
| 🎚️ Slider de idade | Seleção de idade entre 0 e 120 anos |
| ⚖️ Entrada de peso | Campo numérico para peso em quilogramas |
| 📏 Entrada de altura | Campo numérico para altura em metros |
| 🧮 Cálculo do IMC | Cálculo automático ao clicar no botão |
| 🏷️ Classificação do IMC | Exibe a categoria correspondente ao IMC calculado |
| 📐 Classificação de altura | Categoriza o usuário como Baixo(a), Mediano(a) ou Alto(a) |
| 🔞 Status de maioridade | Informa se o usuário é maior ou menor de idade |
| 🎨 Interface Dark Mode | Layout estilizado com CSS customizado e tema escuro |
| ⚠️ Validação de entrada | Exibe erro caso a altura informada seja inválida (≤ 0) |

---

## 🔧 Pré-requisitos

### Google Colab
Nenhuma instalação necessária. Todas as dependências já estão disponíveis no ambiente Colab.

### Jupyter Notebook / JupyterLab (local)

Instale as dependências com:

```bash
pip install ipywidgets
```

Para habilitar os widgets no Jupyter clássico:

```bash
jupyter nbextension enable --py widgetsnbextension
```

Para JupyterLab:

```bash
jupyter labextension install @jupyter-widgets/jupyterlab-manager
```

### Versões recomendadas

| Biblioteca | Versão mínima |
|---|---|
| Python | 3.7+ |
| ipywidgets | 7.0+ |
| IPython | 7.0+ |

---

## 🚀 Como Usar

### Via Google Colab

1. Acesse o notebook pelo link:  
   [🔗 Abrir no Google Colab](https://colab.research.google.com/drive/1PA-4w1RV_EMogSC1FVUrDARDNifA00FX)

2. No menu superior, clique em **"Ambiente de execução" → "Executar tudo"** (`Ctrl+F9`).

3. A interface interativa será exibida diretamente abaixo da célula.

### Via Jupyter Local

1. Clone ou baixe o arquivo `.ipynb` para sua máquina.

2. Abra o terminal na pasta do projeto e execute:

```bash
jupyter notebook IMCipynb.ipynb
```

3. Execute todas as células (`Kernel → Restart & Run All`).

4. Preencha os campos na interface exibida:
   - **Nome**: Digite seu nome
   - **Idade**: Ajuste o slider
   - **Peso (kg)**: Informe seu peso
   - **Altura (m)**: Informe sua altura (ex.: `1.75`)

5. Clique em **"Calcular Resultados"** para visualizar o diagnóstico.

---

## 🗂️ Estrutura do Código

```
imcipynb.py
│
├── style (str)              # CSS injetado para estilização dark mode
│
├── Widgets de Entrada
│   ├── nome_w               # widgets.Text — nome do usuário
│   ├── idade_w              # widgets.IntSlider — idade (0–120)
│   ├── peso_w               # widgets.FloatText — peso em kg
│   └── altura_w             # widgets.FloatText — altura em metros
│
├── btn_calcular             # widgets.Button — dispara o cálculo
│
├── out                      # widgets.Output — área de saída dinâmica
│
├── processar_dados(b)       # Função callback vinculada ao botão
│   ├── Lê os valores dos widgets
│   ├── Classifica maioridade
│   ├── Classifica altura
│   ├── Calcula e classifica o IMC
│   └── Exibe resultado formatado em HTML
│
└── form (VBox)              # Layout vertical agrupando todos os widgets
```

---

## 📊 Lógica de Classificação

### IMC (Índice de Massa Corporal)

A fórmula utilizada é a padrão da **Organização Mundial da Saúde (OMS)**:

```
IMC = Peso (kg) / Altura² (m)
```

| Faixa de IMC | Classificação |
|---|---|
| IMC < 18,5 | Abaixo do peso |
| 18,5 ≤ IMC < 24,9 | Peso normal |
| 25,0 ≤ IMC < 29,9 | Sobrepeso |
| IMC ≥ 30,0 | Obesidade |

> ⚕️ **Aviso**: Este cálculo é apenas informativo. Consulte um profissional de saúde para avaliação completa.

### Classificação de Altura

| Faixa | Categoria |
|---|---|
| Altura ≤ 1,65 m | Baixo(a) |
| 1,65 m < Altura ≤ 1,79 m | Mediano(a) |
| Altura > 1,79 m | Alto(a) |

### Classificação de Maioridade

| Condição | Status |
|---|---|
| Idade ≥ 18 | Maior de idade |
| Idade < 18 | Menor de idade |

---

## 🎨 Interface

A interface adota um tema **dark mode** com as seguintes características visuais:

- **Fundo principal**: `#1e1e1e` (cinza escuro)
- **Fundo da área de saída**: `#2d2d2d`
- **Cor de destaque**: `#007bff` (azul primário)
- **Tipografia**: `Segoe UI`, Tahoma, Geneva, Verdana (sans-serif)
- **Borda lateral de resultado**: `5px solid #007bff`
- **Botão de ação**: estilizado com `button_style='primary'` + CSS customizado

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Função |
|---|---|
| **Python 3** | Linguagem base |
| **ipywidgets** | Componentes interativos no notebook |
| **IPython.display** | Renderização de HTML e exibição de widgets |
| **Google Colab** | Ambiente de execução em nuvem |
| **Jupyter Notebook** | Ambiente de execução local |
| **HTML/CSS** | Estilização da interface |

---

## 💡 Possíveis Melhorias

- [ ] Adicionar gráfico de gauge visual para o IMC com `matplotlib` ou `plotly`
- [ ] Incluir campo de seleção de sexo biológico para cálculos mais precisos
- [ ] Exportar o resultado como PDF ou imagem
- [ ] Adicionar histórico de medições com `pandas` e `DataFrame`
- [ ] Internacionalização (suporte a inglês e espanhol)
- [ ] Validação de intervalo para peso e altura (evitar valores absurdos)
- [ ] Adicionar recomendações nutricionais básicas por faixa de IMC

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Sinta-se livre para usar, modificar e distribuir conforme necessário.

---

<div align="center">
  Desenvolvido com 🐍 Python + 📓 Jupyter / Google Colab
</div>
