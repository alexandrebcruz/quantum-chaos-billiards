# equacao_logistica2

> **Versão para leitura (2026)** do notebook [`equacao_logistica2.nb`](equacao_logistica2.nb), escrito no Mathematica 9 em 2015. O código das células de entrada foi transcrito para texto; os gráficos foram redesenhados em Python a partir dos pontos e polígonos salvos no próprio notebook, então cores, iluminação e eixos podem diferir um pouco do original. Os avisos do Mathematica foram omitidos. Para executar, abra o `.nb` no Mathematica ou no Wolfram Player, que é gratuito.

```mathematica
Quit;
r = 4;
a = 0.5;
f[x_] = r x (1 - x);
DSolve[{x'[t] == f[x[t]], x[0] == a}, x[t], t]
g[t_] = (1/a) f[(a E^(r t))/(1 - a + a E^(r t))] // FullSimplify // Factor
Limit[(1/t) Log[Sqrt[g[t]^2]], t -> ∞]
```

```text
{{x[t] -> (E^(4 t))/(1 + E^(4 t))}}
2. Sech[2 t]^2
-4.
```
