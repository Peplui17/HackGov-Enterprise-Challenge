# 🏛️ HackGov - Plataforma Analítica e Preditiva para Gestão Pública

> **Enterprise Challenge - Fase 4 (Entrega Final do Produto)**  
> **Autor / Aluno:** Luiz Otávio Villas Bôas Ramos Tondin Fontes (RM: 561537)  
> **Apresentação em Vídeo:** [Assista no YouTube](https://youtu.be/6Qb4tDQavSY)  
> **Repositório Oficial:** [github.com/Peplui17/HackGov](https://github.com/Peplui17/HackGov)

---

## 📌 Visão Geral do Produto

O **HackGov** é uma solução de gestão pública que evoluiu de um sistema reativo de registros de ocorrências para uma **plataforma analítica e preditiva**. 

A solução integra os dados operacionais das solicitações dos cidadãos aos órgãos municipais, utilizando **Estatística Descritiva**, **Machine Learning** e **Processamento de Linguagem Natural (PLN)**. Com isso, permite que os gestores públicos monitorem prazos de atendimento (SLA), identifiquem gargalos crônicos em bairros específicos, prevejam quebras de prazo e realizem a triagem automática de chamados.

---

## 🏛️ Esquema de Dados (Oracle Database)

O modelo relacional da aplicação é composto por 7 tabelas operacionais:
- **`SOLICITACAO`**: Registro central das ocorrências urbanas.
- **`TIPO_OCORRENCIA`**: Tipificação das demandas, secretaria responsável e SLA em dias.
- **`HISTORICO_STATUS`**: Rastreabilidade e ciclo de vida de cada chamado (`Aberto`, `Em Atendimento`, `Concluído`).
- **`CIDADAO`**: Dados do solicitante público.
- **`FUNCIONARIO`**: Agente público responsável pelo atendimento do chamado.
- **`USUARIO_SISTEMA`**: Credenciais e acessos do painel administrativo.
- **`EVIDENCIA_FOTO`**: Anexos multimídia enviados pelos cidadãos para comprovação e triagem.

---

## 🎯 Módulos de Ciência de Dados & IA (Python 3.13)

1. **Fase 1 - Estatística Descritiva e SLA:**
   - Cálculo de média de atendimento, variância e desvio padrão dos prazos de SLA por tipo de ocorrência.
   - Cruzamento do impacto de evidências fotográficas (`EVIDENCIA_FOTO`) na resolução de chamados.
   - Geração automática de histogramas de frequência e gráficos de dispersão por bairro (`Matplotlib` / `Seaborn`).

2. **Fase 2 - Machine Learning Preditivo & Agrupamento:**
   - **Predição de Quebra de SLA:** Classificador `Random Forest` (`Scikit-Learn`) para estimar a probabilidade de atraso de novas solicitações.
   - **Clusterização Regional:** Algoritmo `K-Means` para agrupar bairros com perfil de problemas públicos e tempo de resposta similares.

3. **Fase 3 - Processamento de Linguagem Natural (PLN):**
   - Classificação textual supervisionada (`TF-IDF` + `Naive Bayes`) das descrições dos cidadãos para identificação automática da **Secretaria Responsável** e do **Grau de Urgência**.

---

## 🛠️ Tecnologias e Arquitetura

- **Linguagem:** Python 3.13
- **Manipulação de Dados:** Pandas, NumPy, SciPy
- **Visualização:** Matplotlib, Seaborn
- **Machine Learning & PLN:** Scikit-Learn
- **Backend:** Java 17 (Spring Boot)
- **Banco de Dados Relacional:** Oracle Database (`oracledb`)

---
