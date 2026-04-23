# Credit-Card-Deposit-Transaction_Analytics
Conducted payment analytics focused on approval rates, chargebacks, and risk. Identified a sustained decline in approval rates (Q4 2020–Q3 2021) with no increase in fraud levels. Analysis indicates key drivers such as issuing bank behavior, antifraud settings, and changes in customer risk profile. Performed cohort, funnel, and behavioral analysis to uncover actionable insights.

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



This project presents an analytical dashboard and executive summary focused on credit card deposit transactions over a 12-month period. The analysis explores key performance indicators such as approval rates, chargeback rates, customer behavior, and issuing bank performance.

A clear downward trend in approval rates is identified, decreasing from 62.9% in Q4 2020 to 59.4% in Q3 2021, suggesting a structural shift rather than random fluctuation. In contrast, chargeback rates remain relatively stable, indicating no significant increase in fraud pressure.

The project also highlights customer cohort behavior, particularly a high-performing segment of $50 deposits in September 2021, and reveals strong variability in approval rates across issuing banks, emphasizing the impact of issuer-specific factors.

Further analysis investigates root causes behind performance changes, including shifts in risk mix, processing configurations, and traffic sources. The study concludes that the decline in approval rates is likely driven by progressive tightening in risk controls rather than a single isolated factor.

Finally, the project outlines advanced analytical approaches, such as bank–processor interaction effects, cohort segmentation, and transaction pattern analysis, to uncover deeper insights and support strategic decision-making.

________________________             ______________________          _______________________

for line in content.split("\n"):
    story.append(Paragraph(line, styles["Normal"]))
    story.append(Spacer(1, 8))

doc = SimpleDocTemplate(doc_path)
doc.build(story)

doc_path
