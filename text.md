Aqui está o texto final do manual, mantendo toda a estrutura que você aprovou e incluindo de forma clara e visual as fórmulas matemáticas apenas nos gráficos onde há cálculo envolvido.

---

# Guia de Interpretação: Dashboard Analítico de Dores Docentes (Versão Final)

Este guia serve como manual de consulta para entender a lógica, a matemática e o significado de cada gráfico presente no dashboard do projeto **IA Educa**.

---

### 1. Seção de Perfil (Filtros e Contexto)

#### **Distribuição por Turno / Nível de IA / Tempo de Experiência**
* **Definição:** Percentual de docentes em cada categoria demográfica.
* **Fórmula matemática:** $$\frac{\text{Contagem da Categoria}}{\text{Total de Respondentes}} \times 100$$
* **Função:** Estabelecer a base da amostra. Permite entender, por exemplo, se a maioria dos respondentes são iniciantes ou veteranos e qual seu nível de maturidade digital.

#### **Distribuição por Modalidade**
* **Definição:** Porcentagem de docentes atuando em cada modelo de ensino (Presencial, Semi-presencial, etc.).
* **Fórmula matemática:** $$\frac{\text{Contagem da Modalidade}}{\text{Total de Respondentes}} \times 100$$
* **Função:** Identificar o cenário de atuação. Dores no ensino semi-presencial podem diferir drasticamente das do ensino presencial 100% prático.

---

### 2. Análise Espacial

#### **Mapa de Participação Geográfica**
* **Definição:** Representação cartográfica das unidades participantes.
* **Função/Significado:** Representa visualmente a **quantidade de professores participantes por unidade** do SENAI Bahia. Quanto mais escura ou intensa a cor da região no mapa, maior foi o volume de engajamento daquela unidade na pesquisa. *(Nota: Por ser uma contagem simples, não requer fórmula complexa).*

---

### 3. Matriz e Ranking de Criticidade

#### **Matriz de Decisão (Gráfico de Dispersão)**
* **Eixos:** Frequência (X) e Impacto (Y).
* **Fórmula matemática (Posição de cada ponto):**
  $$X = \frac{\sum \text{Frequência}}{n} \quad ; \quad Y = \frac{\sum \text{Impacto}}{n}$$
* **Lógica:** Cruza a recorrência média do problema com a gravidade média dele. Desafios no quadrante superior direito são prioridades máximas.

#### **Ranking de Criticidade (Score)**
* **Definição:** Lista ordenada dos desafios com base no cálculo de severidade.
* **Fórmula matemática:** $$Score = \sqrt{\text{Frequência} \times \text{Impacto}}$$
* **Explicação Matemática (Resumo Executivo):**
    * **Escala Intuitiva:** O score usa a raiz quadrada da multiplicação para retornar o resultado à escala original de 1 a 5.
    * **Penalização de Desequilíbrios:** Como utiliza a média geométrica, o score é rigoroso: um desafio só chega ao topo se for **simultaneamente** frequente e grave. Isso evita que problemas raros (baixa frequência) "poluam" o topo do ranking.
    * **Sensibilidade:** Garante que qualquer melhoria em um dos eixos reduza o score final de forma proporcional e equilibrada.

---

### 4. Indicadores de Performance (KPIs)

#### **Taxa de Dor Aguda (TDA %)**
* **Definição:** Percentual de docentes que sofrem com o impacto máximo daquele desafio.
* **Fórmula matemática:** $$TDA = \left( \frac{\text{Docentes com Freq} \ge 4 \text{ E Impacto} \ge 4}{\text{Total de Respondentes}} \right) \times 100$$
* **Função:** Identificar onde o "sofrimento" docente é unânime e paralisante.

#### **Índice de Potencial de Automação (IPA)**
* **Categorização Explícita:**
    * **Alto (Automatizável):** Desafios técnicos e repetitivos: *Dúvidas recorrentes*, *Correção de atividades*, *Adaptação do planejamento*, *Dificuldade de planejar aulas* e *Sobrecarga com dúvidas comuns*.
    * **Baixo (Socioemocional/Complexo):** Desafios que exigem mediação humana: *Engajamento*, *Comportamento*, *Desnivelamento da turma* e *Falta de propósito do aluno*.
* **Função:** Separar o que a tecnologia pode resolver (automação) do que exige intervenção pedagógica humana. *(Nota: A classificação é feita via regras de texto/palavras-chave).*

---

### 5. Correlações Analíticas

#### **Nível de IA vs Score Médio de Criticidade**
* **Fórmula matemática:** $$\text{Média do Score} = \frac{\sum \text{Scores de Criticidade}}{\text{Total de Docentes no Nível de IA}}$$
* **Função:** Verifica se o conhecimento em IA reduz a percepção de dor. Se a barra de "Avançado" for menor que a de "Básico", a IA está agindo como um mitigador de problemas.

#### **Impacto da Autonomia vs Nível de IA (Média)**
* **Definição:** Gráfico de barras que exibe a média da nota de impacto do desafio "Dificuldade em gerar autonomia" para cada nível de fluência em IA.
* **Fórmula matemática:** $$\text{Média de Impacto} = \frac{\sum \text{Notas de Impacto}}{\text{Número de Docentes no Grupo}}$$
* **Função:** Validar se docentes mais fluentes em IA conseguem lidar melhor com a falta de autonomia dos alunos, sentindo um impacto menor nas suas atividades.

#### **Heatmap: Áreas vs Top 5 Dores**
* **Fórmula matemática (Cálculo da Célula de Calor):** $$\text{Valor da Célula} = \frac{\sum \text{Scores da Dor 'X' na Área 'Y'}}{\text{Total de Docentes da Área 'Y'}}$$
* **Função:** Mapa de calor que mostra em quais áreas técnicas cada dor é mais forte. Serve para criar planos de ação customizados (ex: uma solução para a área de Alimentos pode ser diferente da área de TI).