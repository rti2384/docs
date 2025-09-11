# Removing the Spread (De‑juicing)

Suppose a sportsbook offers A at +120 and B at −145.

- For +x odds: p = 100/(x + 100)
- For −y odds: p = y/(y + 100)

Thus:
- p*_A = 100/(120+100) ≈ 45.45%
- p*_B = 145/(145+100) ≈ 59.18%
- p*_A + p*_B = 104.63% → embedded vig

Normalize:
- p_A = p*_A/(p*_A+p*_B) ≈ 43.44%
- p_B = p*_B/(p*_A+p*_B) ≈ 56.56%

Converted back to American odds: ≈ +131 and −131.
