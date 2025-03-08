# Covered Interest Parity

### In this project, I researched the CIP arbitrage and used data sourced from Bloomberg to investigate the largest CIP spread deviations over the past decade.
### The currencies in question were the Swiss Franc (CHF), Euro (EUR), Pound (GBP), New Zealand Dollar (NZD), Australian Dollar (AUD), Swedish Krona (SEK), Japanese Yen (JPY), and Canadian Dollar (CAD).

* Data was comprised of OIS (overnight indexed swap) rates, spot rates for USD/CCY, and forward **points**, which I converted to 3-month forward rates using standard conventions -->
  $$
  \[F_t = S_t + \frac{\text{FP}_t}{\begin{cases} 
    10,000, & \text{for most currency pairs (EUR, GBP, AUD, etc.)} \\
    100, & \text{for JPY}
\end{cases}}
$$
where $F_t$ denotes the 3-month forward rate, $S_t$ denotes the spot rate, and $FP_t$ denotes the forward points.
* Then, 
