# **Covered Interest Parity (CIP) Arbitrage Analysis**

### **Overview**
This project investigates **Covered Interest Parity (CIP) arbitrage** using historical data sourced from Bloomberg. The analysis focuses on deviations from CIP and examines arbitrage opportunities across major currency pairs.

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

## **Methodology: CIP Calculation**

Covered Interest Parity (CIP) states that the interest rate differential between two currencies should be reflected in the forward exchange rate. Any deviation from CIP presents an arbitrage opportunity.

The CIP deviation is defined as:

$
\text{CIP}^{c}_{t,\tau} \equiv y^{\$}_{t,\tau} - \left( y^{c}_{t,\tau} - \rho^{c}_{t,\tau} \right).
$

where:
- \( y^{\$}_{t,\tau} \) is the **continuously compounded risk-free rate** in USD.
- \( y^{c}_{t,\tau} \) is the **foreign currency risk-free rate**.
- \( \rho^{c}_{t,\tau} \) is the **forward premium**, computed as:

$
\rho^{c}_{t,\tau} = \frac{1}{\tau} \left( f^{c}_{t,\tau} - s^{c}_{t} \right).
$

where:
- \( $f^{c}_{t,\tau} $\) is the **log forward exchange rate**.
- \( $s^{c}_{t} $\) is the **log spot exchange rate**.
- \( $\tau $\) represents the **tenor** of the forward contract.

To compute the **forward rate from forward points**, we use the standard market convention:

$$
F_t = S_t + \frac{\text{FP}_t}{\begin{cases} 
    10,000, & \text{for most currency pairs (EUR, GBP, AUD, etc.)} \\
    100, & \text{for JPY}
\end{cases}}
$$

where:
- \( $F_t$ \) = 3-month forward exchange rate
- \( $S_t$ \) = Spot exchange rate
- \( $FP_t$ \) = Forward points

We use **Overnight Indexed Swap (OIS) rates** as the benchmark risk-free rate.

---

## **Results: CIP Arbitrage Spreads**
The following figure presents the **time-series of arbitrage spreads** for the selected currencies:

![CIP Arbitrage Spreads](path_to_your_plot.png)

### **Description of the Plot**
- The y-axis represents the **CIP deviation** (arbitrage spread) in **basis points (bps)**.
- The x-axis represents the **timeline** (2010–2020).
- A **positive CIP deviation** indicates an arbitrage opportunity where synthetic funding is cheaper than direct USD funding.
- A **negative CIP deviation** suggests that direct USD funding is cheaper than synthetic funding.
- Large spikes (e.g., during the 2008–09 financial crisis and COVID-19 period) indicate periods of **market stress and liquidity constraints**.

---

## **Key Takeaways**
✅ CIP deviations persist even in modern financial markets, contrary to theory.  
✅ Deviations widen during **market distress**, reflecting funding liquidity constraints.  
✅ The magnitude of deviations varies across currencies, with JPY and CHF showing larger anomalies.  

---

## **Data Sources**
- **Spot exchange rates** (USD/CCY pairs)
- **Forward points** (converted to forward rates)
- **OIS rates** (used as risk-free rates)

All data was obtained from Bloomberg.

---

## **Future Work**
- Investigate how **cross-currency basis swaps** impact CIP deviations.
- Analyze **high-frequency data** for intra-day arbitrage opportunities.
- Explore the impact of **central bank interventions** on CIP deviations.

---

## **References**
- Du et al. (2018), *"Deviations from Covered Interest Parity"*, Journal of Finance.
- Rime et al. (2017), *"Interbank Market Liquidity and Arbitrage Spreads"*, BIS Working Paper.

---
