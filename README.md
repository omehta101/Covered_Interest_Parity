# **Covered Interest Parity**

### **Overview**
In this project, I researched Covered Interest Parity (CIP) arbitrage and used data sourced from Bloomberg to investigate the largest CIP spread deviations over the past decade.

The currencies analyzed include:
- **Swiss Franc (CHF)**
- **Euro (EUR)**
- **Pound Sterling (GBP)**
- **New Zealand Dollar (NZD)**
- **Australian Dollar (AUD)**
- **Swedish Krona (SEK)**
- **Japanese Yen (JPY)**
- **Canadian Dollar (CAD)**

---

### **Data Sources & Processing**
The dataset consists of:
- **Overnight Indexed Swap (OIS) rates**  
- **Spot exchange rates** for USD/CCY pairs  
- **Forward points**, which were converted into 3-month forward rates using standard market conventions:

$$
F_t = S_t + \frac{\text{FP}_t}{\begin{cases} 
    10,000, & \text{for most currency pairs (EUR, GBP, AUD, etc.)} \\
    100, & \text{for JPY}
\end{cases}}
$$

where:  
- \( F_t \) = 3-month forward rate  
- \( S_t \) = Spot exchange rate  
- \( FP_t \) = Forward points  

---
