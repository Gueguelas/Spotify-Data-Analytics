---

# 🎧 Spotify Data Analytics

> Análise exploratória e modelagem preditiva baseada no histórico pessoal de streaming do Spotify.

---

## 📌 Sobre o Projeto

Este projeto realiza uma análise completa dos dados de streaming do Spotify, desde o processamento de dados brutos (`raw`) até modelagem preditiva utilizando Machine Learning.

O objetivo é:

* 📊 Entender padrões de consumo musical
* 🎶 Identificar gêneros, artistas e comportamentos de escuta
* 🤖 Construir modelos preditivos para:

  * Prever **tempo de reprodução**
  * Prever **probabilidade de skip**

---

## 🗂️ Estrutura do Projeto

```bash
Spotify-Data-Analytics/
│
├── data/
│   ├── raw/                # Histórico bruto exportado do Spotify (JSON)
│   └── spotify-api/        # Dados enriquecidos via API (artistas, gêneros, ids)
│
├── notebooks/
│   ├── analise_exploratoria_spotify.ipynb
│   ├── get_data_from_spotify_api.ipynb
│   ├── feature_importance_minutes_played.ipynb
│   ├── feature_importance_feature_skip.ipynb
│   └── models.ipynb
├── data_catalog.yaml
└── README.md
```

---

## 📦 Modelo dos Dados (RAW)

Os arquivos da pasta `data/raw/` são exportações oficiais do Spotify no formato JSON.

Cada registro contém informações como:

| Campo                               | Descrição                               |
| ----------------------------------- | --------------------------------------- |
| `ts`                                | Timestamp da reprodução                 |
| `ms_played`                         | Tempo tocado da música em milissegundos |
| `platform`                          | Plataforma utilizada                    |
| `conn_country`                      | País da conexão                         |
| `ip_addr`                           | IP da sessão                            |
| `master_metadata_track_name`        | Nome da música                          |
| `master_metadata_album_artist_name` | Nome do artista                         |
| `master_metadata_album_album_name`  | Nome do álbum                           |
| `spotify_track_uri`                 | URI da faixa no Spotify                 |

Esses dados servem como base primária para toda a análise.

---

## 🔌 Enriquecimento com API do Spotify

A pasta `data/spotify-api/` contém dados adicionais obtidos via API:

* 🎤 `unique_artists.json` → Lista de artistas únicos extraídos do raw
* 🆔 `artist_id_map.json` → Mapeamento nome → ID do Spotify
* 🎼 `artists_genres_and_id.json` → Artistas com seus respectivos gêneros

Isso permite:

* Adicionar coluna de **gênero musical**
* Criar variáveis mais robustas para modelagem
* Melhorar a qualidade da análise exploratória

---

# 📓 Notebooks

## 1️⃣ `get_data_from_spotify_api.ipynb`

Responsável por:

* Extrair artistas únicos
* Consultar API do Spotify
* Obter IDs e gêneros
* Criar base enriquecida

📌 Resultado: dataset com coluna de gênero pronta para análise.

---

## 2️⃣ `analise_exploratoria_spotify.ipynb`

Análise exploratória completa:

* Distribuição de tempo tocado
* Análise por gênero
* Frequência de artistas
* Comportamento de skip
* Estatísticas descritivas
* Agrupamentos por usuário e gênero

📊 Objetivo: entender padrões e gerar insights.

---

## 3️⃣ `feature_importance_minutes_played.ipynb`

Modelo preditivo para:

🎯 Prever o tempo de reprodução (`ms_played`)

Inclui:

* Engenharia de features
* Treinamento de modelo
* Avaliação
* Análise de importância das variáveis

---

## 4️⃣ `feature_importance_feature_skip.ipynb`

Modelo para prever:

⏭️ Se uma música será pulada (skip)

Inclui:

* Criação da variável target
* Balanceamento
* Treinamento
* Feature importance
* Avaliação do modelo

---

## 5️⃣ `models.ipynb`

Notebook consolidado de modelagem:

* Comparação de modelos
* Métricas de performance
* Avaliação final
* Seleção de modelo ideal

---

# 🧠 Técnicas Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib / Seaborn
* Scikit-learn
* API REST (Spotify)
* Feature Engineering
* Modelos de Regressão
* Modelos de Classificação

---

# 📊 Pipeline do Projeto

```text
RAW JSON
   ↓
Enriquecimento com API
   ↓
Limpeza e Tratamento
   ↓
Análise Exploratória
   ↓
Feature Engineering
   ↓
Modelagem Preditiva
   ↓
Avaliação
```

---

# 🚀 Principais Insights Possíveis

* Gêneros mais ouvidos
* Padrão de escuta ao longo dos anos
* Probabilidade de skip por gênero
* Artistas com maior retenção
* Variáveis que mais influenciam tempo de reprodução

---

# 📈 Possíveis Melhorias Futuras

* Deploy como dashboard (Streamlit / Dash)
* Sistema de recomendação personalizado
* Clusterização de perfil musical
* Deploy do modelo como API

---

# 🎯 Objetivo Profissional

Este projeto demonstra:

* Capacidade de manipular grandes volumes de dados
* Integração com APIs externas
* Construção de pipeline analítico completo
* Aplicação de Machine Learning em problema real
* Organização e estruturação de projeto de dados

---