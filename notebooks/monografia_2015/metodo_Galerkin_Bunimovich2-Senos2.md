# metodo_Galerkin_Bunimovich2-Senos2

> **Versão para leitura (2026)** do notebook [`metodo_Galerkin_Bunimovich2-Senos2.nb`](metodo_Galerkin_Bunimovich2-Senos2.nb), escrito no Mathematica 9 em 2015. O código das células de entrada foi transcrito para texto; os gráficos foram redesenhados em Python a partir dos pontos e polígonos salvos no próprio notebook, então cores, iluminação e eixos podem diferir um pouco do original. Os avisos do Mathematica foram omitidos. Para executar, abra o `.nb` no Mathematica ou no Wolfram Player, que é gratuito.

```mathematica
a = 1;
b = 1;
φ[x_, y_, n_, m_] = Sin[π*n ((x + Sqrt[y (b - y)])/(a + 2 Sqrt[y (b - y)]))] Sin[π*m (y/b)]
nM = 3;
mM = 3;
Base[x_, y_] = Table[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM], {i, 0, nM*mM - 1}];
A[k_] = Table[NIntegrate[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM] Laplacian[φ[x, y, 1 + Mod[j, nM], 1 + (j - Mod[j, nM])/mM], {x, y}], {y, 0, b}, {x, -Sqrt[y (b - y)], a + Sqrt[y (b - y)]}, AccuracyGoal -> 10] + k^2 NIntegrate[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM] φ[x, y, 1 + Mod[j, nM], 1 + (j - Mod[j, nM])/mM], {y, 0, b}, {x, -Sqrt[y (b - y)], a + Sqrt[y (b - y)]}, AccuracyGoal -> 10], {i, 0, nM*mM - 1}, {j, 0, nM*mM - 1}];
A[k] // MatrixForm
Vka = Solve[Det[A[k]] == 0 && k >= 0, k]
ka = 3.5798254566173036`;
Vc[ka] = NullSpace[N[A[ka], 10]] ;
id = 1;
v = Vc[ka][[id]];
ϕ[x_, y_] = Base[x, y].v
Plot3D[ϕ[x, y], {x, -b/2, a + (b/2)}, {y, 0, b}, RegionFunction -> Function[{x, y, z}, -Sqrt[y (b - y)] <= x <= a + Sqrt[y (b - y)]]]
ContourPlot[ϕ[x, y], {x, -b/2, a + (b/2)}, {y, 0, b}, RegionFunction -> Function[{x, y, z}, -Sqrt[y (b - y)] <= x <= a + Sqrt[y (b - y)]]]
```
