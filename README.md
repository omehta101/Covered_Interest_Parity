# **Covered Interest Parity (CIP) Arbitrage Analysis**

Covered Interest Parity (CIP) states that the interest rate differential between two currencies should be reflected in the forward exchange rate. Any deviation from CIP presents an arbitrage opportunity.

The CIP deviation is defined as:

\[
\text{CIP}^{c}_{t,\tau} \equiv y^{\$}_{t,\tau} - \left( y^{c}_{t,\tau} - \rho^{c}_{t,\tau} \right)
\]

where:
- \( y^{\$}_{t,\tau} \) is the **continuously compounded risk-free rate** in USD.
- \( y^{c}_{t,\tau} \) is the **foreign currency risk-free rate**.
- \( \rho^{c}_{t,\tau} \) is the **forward premium**, computed as:

\[
\rho^{c}_{t,\tau} = \frac{1}{\tau} \left( f^{c}_{t,\tau} - s^{c}_{t} \right)
\]

where:
- \( f^{c}_{t,\tau} \) is the **log forward exchange rate**.
- \( s^{c}_{t} \) is the **log spot exchange rate**.
- \( \tau \) represents the **tenor** of the forward contract.

To compute the **forward rate from forward points**, we use the standard market convention:

\[
F_t = S_t + \frac{\text{FP}_t}{\begin{cases} 
    10,000, & \text{for most currency pairs (EUR, GBP, AUD, etc.)} \\
    100, & \text{for JPY}
\end{cases}}
\]

where:
- \( F_t \) = 3-month forward exchange rate  
- \( S_t \) = Spot exchange rate  
- \( FP_t \) = Forward points  
