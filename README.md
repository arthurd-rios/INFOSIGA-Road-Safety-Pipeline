# 🚑 MVP - Sistema de Otimização Tática de Recursos Rodoviários (SP-270)

> **Uma ferramenta de inteligência geográfica para alocação preventiva de viaturas e redução de tempo de resposta em rodovias.**

## 🎯 O Problema
Concessionárias de rodovias enfrentam o desafio de posicionar ambulâncias e guinchos em uma malha extensa. O posicionamento reativo (esperar o acidente acontecer) aumenta o tempo de resposta e o risco de congestionamentos secundários, especialmente em trechos de alta densidade urbana como a Grande SP.

## 💡 A Solução
Este projeto utiliza dados históricos do **Infosiga (2022-2025)** e enriquecimento via **OpenStreetMap** para treinar um modelo de Machine Learning que prevê "Hotspots de Risco" dinâmicos.

O resultado final é um **Mapa Temporal (Time-Lapse)** que permite aos gestores do CCO (Centro de Controle Operacional) visualizar onde a probabilidade de acidentes é maior em cada hora do dia e dia da semana.

## 🛠️ Stack Tecnológica & Metodologia
* **Coleta & Limpeza:** Pandas, Geopandas.
* **Enriquecimento de Dados:** `Pyrosm` (para extrair features da infraestrutura da pista como faixas, limites de velocidade e geometria diretamente do OpenStreetMap).
* **Modelagem:** Scikit-Learn (Random Forest Classifier para Risco e Regressor para Severidade).
* **Técnica de Sampling:** Geração de dados sintéticos de "não-acidentes" para balanceamento e cálculo real de probabilidade de risco.
* **Visualização:** Folium (TimestampedGeoJson) para renderização espaço-temporal.

## 📂 Estrutura do Projeto
1.  **Exploração:** Análise inicial e filtragem.
2.  **Pre-processamento:** Limpeza, georreferenciamento e fusão com malha viária do OSM.
3.  **Data Generation:** Criação de amostras negativas para treino supervisionado.
4.  **Modelagem:** Treinamento e validação dos modelos preditivos.
5.  **Simulação:** Testes de cenários e validação estatística.
6.  **Protótipo Operacional:** Geração do mapa interativo final para uso tático.

## 🚀 Roadmap (V2)
Este é um MVP focado em fatores estruturais e temporais. Uma possível próxima versão poderia possuir:
* [ ] Integração com uma API de clima para ingestão de dados meteorológicos históricos (precisão de chuva/neblina).
* [ ] Refinamento de sazonalidade escolar para diferenciar fluxo de férias vs. letivo.

## 🗺️ Visualização Geoespacial

Você pode interagir com o protótipo operacional através dos links abaixo:

- 🔗 **[Acessar Mapa Interativo (GitHub Pages)](https://arthurd-rios.github.io/INFOSIGA-Road-Safety-Pipeline/animated_map.html)**
- 🔗 **[Visualizar via NbViewer](https://nbviewer.org/github/arthurd-rios/INFOSIGA-Road-Safety-Pipeline/blob/main/animated_map.html)**


Os dados pesados podem ser baixados na aba [Releases] deste repositório.

---
*Projeto desenvolvido por Arthur Domingues Rios - Estudante de Ciência da Computação (USP/ICMC)* # INFOSIGA-Road-Safety-Pipeline
