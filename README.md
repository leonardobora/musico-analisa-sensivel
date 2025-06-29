# 🎵 Sistema de Classificação Musical - Execução 100% Local

> Sistema automatizado para classificação de misoginia em letras musicais usando CNN ultra-compacta. **Totalmente offline - sem dependências de serviços externos.**

## 📋 Sobre o Projeto

Sistema desenvolvido para a **Atividade Discente Supervisionada 2 (ADS2)** da disciplina de **Aprendizado de Máquina**, sob orientação do **Prof. Mozart Hasse**. O projeto implementa uma **Rede Neural Convolucional (CNN)** para detectar conteúdo misógino em letras de música do dataset "Top 100 Songs & Lyrics By Year (1959–2023)".

### 🎯 Objetivo

Criar um modelo de classificação automática que analisa letras de músicas e atribui uma **pontuação de intensidade de conteúdo misógino** na escala de 0 a 1, onde:
- **0**: música sem conteúdo inapropriado
- **1**: letra com conteúdo flagrantemente misógino

## 🏫 Instituição de Ensino

**UniBrasil Centro Universitário**

## 👥 Equipe de Desenvolvimento

**Curso:** Engenharia de Software - 7º Período - Turma B

| Nome | Papel | Responsabilidades |
|------|-------|-------------------|
| **Leonardo Bora** | Desenvolvedor Full-Stack | Arquitetura do sistema, modelagem CNN |
| **Letícia Campos** | Especialista em ML | Treinamento de modelos, análise de dados |
| **Carlos Krueger** | Desenvolvedor Frontend | Interface do usuário, visualizações |
| **Luan constâncio** | Desenvolvedor Backend | APIs, integração de dados |
| **Nathan Correia** | Analista de Dados | Rotulagem manual, pré-processamento |

## 🚀 Tecnologias Utilizadas - **EXECUÇÃO 100% LOCAL**

- **Frontend**: React 18 + TypeScript + Vite
- **UI Components**: Shadcn/UI + TailwindCSS  
- **Machine Learning**: TensorFlow.js (execução no navegador)
- **Banco de Dados**: IndexedDB (armazenamento local do navegador)
- **Dataset**: CSV incluído no projeto (6.000+ músicas)
- **Dependências**: Zero dependências online após instalação

## 🏗️ Arquitetura do Sistema

### Componentes Principais

1. **Interface Web Responsiva**
   - Dashboard analítico
   - Classificador em tempo real
   - Sistema de rotulagem manual
   - Gerenciamento de dados

2. **Modelo CNN Local**
   - Arquitetura personalizada para texto
   - Treinamento 100% local
   - Predição em tempo real
   - Armazenamento persistente

3. **Pipeline de Dados**
   - Pré-processamento de texto
   - Tokenização e vetorização
   - Validação e limpeza

## 💻 Instalação e Configuração Local

### Pré-requisitos

#### Windows
- **Node.js 18+**: [Download](https://nodejs.org/)
- **Git**: [Download](https://git-scm.com/download/win)
- **VSCode** (recomendado): [Download](https://code.visualstudio.com/)

#### Linux (Ubuntu/Debian)
```bash
# Atualizar repositórios
sudo apt update

# Instalar Node.js 18+
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs

# Instalar Git
sudo apt install git

# Verificar instalações
node --version
npm --version
git --version
```

#### Linux (CentOS/RHEL/Fedora)
```bash
# Instalar Node.js 18+
curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
sudo yum install -y nodejs

# Instalar Git
sudo yum install git
```

### Instalação do Projeto

#### 1. Clone o Repositório
```bash
# Clone o projeto
# Substitua pelo nome correto do repositório
 git clone https://github.com/leonardobora/musico-analisa-sensivel.git
cd musico-analisa-sensivel
```

#### 2. Instale as Dependências
```bash
npm install
```

#### 3. Execute o Projeto
```bash
npm run dev
```

Acesse: `http://localhost:8080`

**Observação:** Não é necessário configurar variáveis de ambiente ou Supabase. Todo o armazenamento é local (IndexedDB).

## 🎵 Dataset

**Fonte:** [Top 100 Songs & Lyrics By Year (1959–2023)](https://www.kaggle.com/datasets/brianblakely/top-100-songs-and-lyrics-from-1959-to2019)

- **Volume:** ~6.500 músicas com letras completas
- **Período:** 1959-2023 (64 anos de música popular)
- **Formato:** CSV com colunas: ano, artista, música, letra, posição no ranking

## 🤖 Metodologia de ML

### Abordagem CNN para Texto

1. **Pré-processamento:**
   - Tokenização de texto
   - Remoção de stopwords
   - Normalização e limpeza
   - Vetorização com embeddings

2. **Arquitetura CNN:**
   - Camadas convolucionais 1D
   - Max pooling temporal
   - Dropout para regularização
   - Camada densa final para classificação

3. **Treinamento:**
   - Dataset rotulado manualmente (30+ músicas)
   - Validação cruzada
   - Métricas: Acurácia, Precisão, Recall, F1-Score

### Critérios de Rotulagem

Baseado em literatura acadêmica sobre detecção de misoginia:

- **Baixo (0.0-0.3):** Conteúdo neutro ou positivo
- **Médio (0.3-0.7):** Linguagem questionável, objetificação sutil
- **Alto (0.7-1.0):** Conteúdo explicitamente misógino

## 🔧 Como Usar

### 1. Rotulagem Manual
- Acesse a aba "Rotulagem"
- Selecione músicas do dataset
- Atribua pontuações de 0 a 1
- Salve as classificações
- **Exportação:** Use o botão de exportar para baixar um arquivo `.json` com seus rótulos
- **Importação:** Use o botão de importar para carregar rótulos previamente salvos (útil para colaboração ou entrega)

#### Formato do arquivo de rótulos (`labels.json`):
```json
[
  {
    "id": "unique_song_id_1",
    "title": "Nome da Música 1",
    "artist": "Nome do Artista 1",
    "year": 2020,
    "lyrics": "Letra da música aqui...",
    "label": "misogynistic"
  }
]
```

### 2. Treinamento do Modelo
- Vá para "Treinamento"
- Configure hiperparâmetros
- Inicie o treinamento local
- Monitore métricas em tempo real

### 3. Classificação Automática
- Use a aba "Classificador"
- Cole letras de música
- Obtenha pontuação automática
- Visualize análise detalhada

### 4. Dashboard Analítico
- Veja estatísticas gerais
- Analise tendências temporais
- Compare resultados

## 📊 Funcionalidades

- ✅ **Classificação em tempo real** com CNN local
- ✅ **Interface web responsiva** e intuitiva
- ✅ **Sistema de rotulagem manual** para treinamento
- ✅ **Dashboard analítico** com visualizações
- ✅ **Gerenciamento de dataset** completo
- ✅ **Treinamento local** sem dependências externas
- ✅ **Métricas de performance** detalhadas
- ✅ **Armazenamento persistente** de modelos

## 🎯 Requisitos Acadêmicos Atendidos

### Técnicos
- [x] Algoritmo de redes neurais artificiais (CNN)
- [x] Execução 100% local (sem serviços externos)
- [x] Análise exploratória do dataset
- [x] Rotulagem manual de 30+ músicas
- [x] Pontuação contínua entre 0 e 1
- [x] Interface funcional para demonstração

### Documentação
- [x] Relatório técnico detalhado
- [x] Justificativas metodológicas com referências
- [x] Análise de limitações éticas e técnicas
- [x] Ranking de músicas classificadas
- [x] Código organizado e comentado
- [x] Apresentação final

## 🚨 Limitações e Considerações Éticas

### Limitações Técnicas
- **Contexto:** Modelo não interpreta contexto complexo ou ironia
- **Tamanho:** Dataset limitado para treinamento robusto
- **Idioma:** Focado apenas em letras em inglês
- **Subjetividade:** Misoginia pode ser interpretada diferentemente

### Limitações Éticas
- **Viés:** Possível viés nos dados de treinamento
- **Interpretação:** Modelo não considera intenção artística
- **Contexto Cultural:** Não considera diferenças culturais/temporais
- **Responsabilidade:** Ferramenta auxiliar, não substitui análise humana

## 📈 Estrutura do Projeto

```
src/
├── components/           # Componentes React
│   ├── ui/              # Componentes de interface
│   ├── ContentClassifier.tsx
│   ├── ModelTraining.tsx
│   ├── ManualLabeling.tsx
│   └── DashboardOverview.tsx
├── services/            # Serviços de ML e dados
│   ├── MisogynyCNNModel.ts
│   ├── TextPreprocessor.ts
│   ├── ModelTrainer.ts
│   └── ModelStorage.ts
├── types/               # Definições TypeScript
└── pages/               # Páginas da aplicação
```

## 🧪 Testes

```bash
# Executar testes unitários
npm run test

# Executar testes de integração
npm run test:integration

# Cobertura de testes
npm run test:coverage
```

## 📚 Referências Acadêmicas

1. Zhang, X., Zhao, J., & LeCun, Y. (2015). Character-level convolutional networks for text classification.
2. Waseem, Z., & Hovy, D. (2016). Hateful symbols or hateful people? Predictive features for hate speech detection on Twitter.
3. Badjatiya, P., et al. (2017). Deep learning for hate speech detection in tweets.
4. Davidson, T., et al. (2017). Hate speech detection with a computational approach.

## 📝 Licença

Este projeto foi desenvolvido para fins acadêmicos como parte da disciplina de Aprendizado de Máquina.

## 🤝 Contribuição

Este é um projeto acadêmico fechado. Para dúvidas ou sugestões, entre em contato com a equipe.

---

**Desenvolvido com ❤️ pela equipe de Engenharia de Software - UniBrasil Centro Universitário 2025**
