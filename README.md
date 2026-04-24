# Credit-Card-Deposit-Transaction_Analytics
Conducted payment analytics focused on approval rates, chargebacks, and risk. Identified a sustained decline in approval rates (Q4 2020–Q3 2021) with no increase in fraud levels. Analysis indicates key drivers such as issuing bank behavior, antifraud settings, and changes in customer risk profile. Performed cohort, funnel, and behavioral analysis to uncover actionable insights.

# Create a PDF using reportlab with the provided content

from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer
from reportlab.lib.styles import getSampleStyleSheet

doc_path = "/mnt/data/payment_analytics_analysis.pdf"

styles = getSampleStyleSheet()
story = []

content = """
b) Chargeback rate by quarter (on approved transactions)
2020 Q4: 8.00%
2021 Q1: 7.66%
2021 Q2: 7.86%
2021 Q3: 7.69%

Relatively stable → the issue is not increasing fraud, but declining approval rates.

c) Customers who attempted a $50 deposit in September 2021
1,803 unique customers

d) Total approved amount from this group (September 2021)
$113,634.87

e) Bank with the highest approval rate (top 10 banks, $150–$999 in 2021)
BANK1002 (~69.8%)

Insight: Significant variation across banks → strong evidence of issuer impact.

f) Main suspects behind the approval rate decline

Issuing bank
Processing company / antifraud system

g) Root causes of the decline (Q3 2021 vs Q4 2020)

Shift in risk mix (transaction size + customer profile)
Increased processing restrictions

The decline is gradual → typical of progressive risk tightening.

h) Factors driving higher chargeback rates.

Repeat customers with suspicious behavior
Specific issuing banks
Certain transaction amounts (e.g., $50)

i) Additional analysis (senior level)

Customer cohort analysis
Bank × processor interaction
Time-based analysis
Value distribution
Retry rate
Full funnel analysis
Fraud segmentation

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
