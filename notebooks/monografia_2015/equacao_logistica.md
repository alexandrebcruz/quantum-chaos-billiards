# equacao_logistica

> **Versão para leitura (2026)** do notebook [`equacao_logistica.nb`](equacao_logistica.nb), escrito no Mathematica 9 em 2015. O código das células de entrada foi transcrito para texto; os gráficos foram redesenhados em Python a partir dos pontos e polígonos salvos no próprio notebook, então cores, iluminação e eixos podem diferir um pouco do original. Os avisos do Mathematica foram omitidos. Para executar, abra o `.nb` no Mathematica ou no Wolfram Player, que é gratuito.

```mathematica
Quit;
f[x_] = r x (1 - x);
n = 2; (* Variavel que define o período do equilíbrio oscilatório *)
 g[x_] = f[x];
For[i = 1 , i < n, i++, g[x_] = Composition[g, f][x]];
g[x] // FullSimplify // Factor
s = Solve[g[x] == x, x] // FullSimplify // Factor
h[x_] = D[g[x], x] // FullSimplify // Factor
For[i = 2 ^(n - 1) + 1 , i <= 2^ n , i++,
	y[r_] = x /. s[[i]];
	Print[z[r_] = h[y[r]] // FullSimplify // Factor];
	Print[Reduce[{Sqrt[z[r]^2] < 1, r > 0}, r] // FullSimplify // Factor] ;
];
```

```text
-r^2 (-1 + x) x (1 - r x + r x^2)
{{x -> 0}, {x -> (-1 + r)/r}, {x -> (1 + r - Sqrt[-3 - 2 r + r^2])/(2 r)}, {x -> (1 + r + Sqrt[-3 - 2 r + r^2])/(2 r)}}
-r^2 (-1 + 2 x) (1 - 2 r x + 2 r x^2)
4 + 2 r - r^2
3 < r < 1 + Sqrt[6]
4 + 2 r - r^2
3 < r < 1 + Sqrt[6]
```
