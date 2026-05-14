## Exercise 16: Prompting using code

### Theoretical background

Code-based prompting leverages a powerful insight: AI models are generally much better at generating correct code than performing calculations or logical operations internally. By explicitly instructing AI to write and explain code that solves a problem (or actually execute code in tools that support it), you bypass the model's less reliable internal "reasoning" for computational tasks and harness its superior code generation capabilities.

This technique is especially valuable for mathematics, data analysis, algorithmic logic, and any task where computational accuracy matters. The code serves as both solution and audit trail—you can verify the logic even if you don't fully understand the model's reasoning process.

### Student task

Identify a problem requiring calculations or algorithmic logic (statistics, optimization, data transformation, etc.). First, ask AI to solve it through natural language reasoning. Then, explicitly ask AI to solve it by writing code (specify language—Python works well). Compare the accuracy and verifiability of both approaches. If you have code execution capability, run the generated code to verify it works.

Try this with progressively more complex computational problems to see where code-based prompting provides maximum value.

### Examples

**Problem:** "Calculate compound interest for $10,000 invested at 7% annual return for 30 years with monthly compounding."

**Natural language approach:**
"Let's calculate this step by step:
- Principal: $10,000
- Rate: 7% annually = 0.07
- Time: 30 years
- Compound monthly means 12 times per year
- Formula: A = P(1 + r/n)^(nt)
- A = 10000(1 + 0.07/12)^(12×30)
- A = 10000(1.00583)^360
- A ≈ 10000 × 7.612
- A ≈ $76,122"
[Approximation, hard to verify steps, potential calculation errors]

**Code-based approach:**
"I'll write Python code to calculate this precisely:

```python
def compound_interest(principal, annual_rate, years, compounds_per_year):
    rate_per_period = annual_rate / compounds_per_year
    num_periods = compounds_per_year * years
    final_amount = principal * (1 + rate_per_period) ** num_periods
    return final_amount

principal = 10000
annual_rate = 0.07
years = 30
compounds_per_year = 12

result = compound_interest(principal, annual_rate, years, compounds_per_year)
print(f'Initial: ${principal:,.2f}')
print(f'Final: ${result:,.2f}')
print(f'Growth: ${result - principal:,.2f}')
print(f'Multiple: {result / principal:.2f}x')
```

Output:
Initial: $10,000.00
Final: $81,165.17
Growth: $71,165.17
Multiple: 8.12x

The investment grows to $81,165.17 after 30 years with monthly compounding."
[Precise, verifiable, shows all intermediate values]

**Complex problem:** "Analyze a dataset of 1000 sales transactions to find: median sale value, top 10% of customers by total spend, correlation between purchase frequency and average order value."

**Natural language approach:**
[Would produce vague descriptions and potentially incorrect statistical interpretations]

**Code-based approach:**
```python
import pandas as pd
import numpy as np

# Assuming data is loaded
# df = pd.read_csv('sales_data.csv')

# 1. Median sale value
median_sale = df['sale_amount'].median()
print(f'Median sale value: ${median_sale:.2f}')

# 2. Top 10% customers by total spend
customer_totals = df.groupby('customer_id')['sale_amount'].sum()
top_10_pct_threshold = customer_totals.quantile(0.90)
top_customers = customer_totals[customer_totals >= top_10_pct_threshold]
print(f'\nTop 10% customers (n={len(top_customers)}):')
print(top_customers.sort_values(ascending=False).head())

# 3. Correlation between purchase frequency and average order value
customer_metrics = df.groupby('customer_id').agg({
    'sale_amount': ['count', 'mean']
}).round(2)
customer_metrics.columns = ['purchase_frequency', 'avg_order_value']
correlation = customer_metrics['purchase_frequency'].corr(
    customer_metrics['avg_order_value']
)
print(f'\nCorrelation between frequency and AOV: {correlation:.3f}')
```
[Precise methodology, reproducible, auditable]

### Gotchas

AI-generated code may be syntactically correct but logically flawed for your specific use case. Always review the logic, not just whether it runs. Code-based responses are longer and may not be necessary for simple arithmetic. Reserve this technique for genuinely computational problems.

If you can't read code in the generated language, you lose the auditability benefit. Specify a language you're familiar with, or ask AI to heavily comment the code.

### Key takeaways

Code-based prompting transforms AI from unreliable calculator into reliable code generator. The technique teaches the important distinction between AI's generative capabilities (excellent) and its computational reliability (moderate). For any task with computational components, asking for code improves both accuracy and transparency.
