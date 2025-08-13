# Monte Carlo Simulation für Optionen
Dieses Projekt Simuliert Aktienpreise mit einer Geometric Brownian Motion 
und berechnet europäische Optionen (Call/Put) mit hilfe von Monte Carlo Simulation

# Hintergrund
Optionen sind Finanzinstrumente, die dem Käufer das Recht (aber nicht die Pflicht) geben,  
einen Basiswert (z. B. eine Aktie) zu einem bestimmten Preis zu kaufen (Call) oder zu verkaufen (Put).  

Der faire Preis einer Option hängt von mehreren Faktoren ab:
- Aktueller Preis des Basiswerts
- Volatilität des Basiswerts
- Risikofreier Zinssatz
- Laufzeit bis zur Fälligkeit

In diesem Projekt wird die Kursentwicklung durch **Geometric Brownian Motion** modelliert,  
und der Optionspreis wird über viele zufällige Kursverläufe per **Monte-Carlo-Simulation** geschätzt.

# Funktionen
1. brownian_motion(T, n_paths, n_steps, seed)                                        
2. geometric_brownian_motion(T, n_paths, n_steps, seed, S_0, mu, o)
3. price_european_call_monte_carlo(T, n_paths, n_steps, seed, S_0, mu, o, r)
4. price_european_put_monte_carlo(T, n_paths, n_steps, seed, S_0, mu, o, r)
5. Visualisierung der simulierten Pfade im Notebook

# Beipsiel parameter
T = 1.0            # laufzeit in Jahren
n_paths = 50       # Anzahl der Simulierten Pfade
n_steps = 1000     # Zeitschritte pro Pfad
mu = 0.05          # Erwartete jährliche Rendite
0 = 0.2            # Volatilität 
r = 0.03           # risikolose Zins
S_0 = 100          # Sartpreis
K = 100            # dStrike-Preis

# Simulation
t, S = geometric_brownian_motion(T, n_paths, n_steps, seed=42, S_0=S_0, mu=mu, sigma=sigma)

# Optionspreis (Call)
call_price = monte_carlo_option_pricing(S, K, r, T, option_type="call")
print("Fairer Call-Preis:", call_price)


