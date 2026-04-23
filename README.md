# Credit-Card-Deposit-Transaction_Analytics
Análise de pagamentos com foco em aprovação, chargeback e risco. Identifiquei queda contínua na aprovação (Q4 2020–Q3 2021) sem aumento de fraude. Evidências apontam impacto de bancos emissores, antifraude e mudança no perfil de risco. Inclui análise de cohort, funil e comportamento.

# Create a PDF using reportlab with the provided content

from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer
from reportlab.lib.styles import getSampleStyleSheet

doc_path = "/mnt/data/payment_analytics_analysis.pdf"

styles = getSampleStyleSheet()
story = []

content = """
a) Taxa de aprovação por trimestre  
2020 Q4: 62,86%  
2021 Q1: 61,48%  
2021 Q2: 60,34%  
2021 Q3: 59,42%  

Queda contínua e consistente — não é ruído, é tendência estrutural.

b) Taxa de chargeback por trimestre (sobre transações aprovadas)  
2020 Q4: 8,00%  
2021 Q1: 7,66%  
2021 Q2: 7,86%  
2021 Q3: 7,69%  

Relativamente estável → o problema não é fraude crescente, mas sim aprovação caindo.

c) Clientes que tentaram depósito de $50 em setembro/2021  
1.803 clientes únicos

d) Valor total aprovado desse grupo (setembro/2021)  
$113.634,87

e) Banco com maior taxa de aprovação (top 10 bancos, $150–$999 em 2021)  
BANK1002 (~69,8%)  

Insight: grande variação entre bancos → forte evidência de impacto do emissor.

f) Suspeitos principais da queda de aprovação  
- Banco emissor  
- Empresa de processamento / antifraude  

g) Causas reais da queda (Q3 2021 vs Q4 2020)  
1. Mudança no mix de risco (valor + perfil de cliente)  
2. Aumento de restrições no processamento  

A queda é gradual → típico de ajuste progressivo de risco.

h) Fatores que aumentam chargeback  
- Clientes recorrentes com comportamento suspeito  
- Certos bancos emissores  
- Valores específicos (ex: $50)

i) Análises adicionais (nível sênior)  
- Cohort de clientes  
- Interação banco + processamento  
- Análise temporal  
- Distribuição de valores  
- Taxa de retry  
- Funil completo  
- Segmentação de fraude  

Frase para entrevista:  
“I would focus on interaction effects between issuing banks and processors, as isolated analysis may hide the real driver.”
"""

for line in content.split("\n"):
    story.append(Paragraph(line, styles["Normal"]))
    story.append(Spacer(1, 8))

doc = SimpleDocTemplate(doc_path)
doc.build(story)

doc_path
