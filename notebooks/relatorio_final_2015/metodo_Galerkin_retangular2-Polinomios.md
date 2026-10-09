# metodo_Galerkin_retangular2-Polinomios

> **Versão para leitura (2026)** do notebook [`metodo_Galerkin_retangular2-Polinomios.nb`](metodo_Galerkin_retangular2-Polinomios.nb), escrito no Mathematica 9 em 2015. O código das células de entrada foi transcrito para texto; os gráficos foram redesenhados em Python a partir dos pontos e polígonos salvos no próprio notebook, então cores, iluminação e eixos podem diferir um pouco do original. Os avisos do Mathematica foram omitidos. Para executar, abra o `.nb` no Mathematica ou no Wolfram Player, que é gratuito.

```mathematica
"definição do retângulo"
a = 1
b = 1
```

```text
1
1
```

```mathematica
"definição da base utilizada"
φ[x_, y_, n_, m_] = x^n (x - a) y^m (y - b)
nM = 2
mM = 2
Base[x_, y_] = Table[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM], {i, 0, nM*mM - 1}]
```

```text
(-1 + x) x^n (-1 + y) y^m
2
2
{(-1 + x) x (-1 + y) y, (-1 + x) x^2 (-1 + y) y, (-1 + x) x (-1 + y) y^2, (-1 + x) x^2 (-1 + y) y^2}
```

```mathematica
"definição da matriz A"
A[k_] = Table[Integrate[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM] Laplacian[φ[x, y, 1 + Mod[j, nM], 1 + (j - Mod[j, nM])/mM], {x, y}], {y, 0, b}, {x, 0, a}] + k^2 Integrate[φ[x, y, 1 + Mod[i, nM], 1 + (i - Mod[i, nM])/mM] φ[x, y, 1 + Mod[j, nM], 1 + (j - Mod[j, nM])/mM], {y, 0, b}, {x, 0, a}] , {i, 0, nM*mM - 1}, {j, 0, nM*mM - 1}]
A[k] // MatrixForm
```

```mathematica
"autovalores obtidos numericamente"
Solve[Det[A[k]] == 0 && k >= 0, k]
```

```text
{{k -> 2 Sqrt[5]}, {k -> 2 Sqrt[13]}, {k -> 2 Sqrt[13]}, {k -> 2 Sqrt[21]}}
```

```mathematica
"autofunções(para um dado autovalor ka) obtidas numericamente: id é um indice de degenerescencia"
ka = 2 Sqrt[13]
Vc[ka] = NullSpace[A[ka]]
id = 2
v = Vc[ka][[id]]
ϕ[x_, y_] = Base[x, y].v
```

```text
2 Sqrt[13]
{{-1/2, 0, 1, 0}, {-1/2, 1, 0, 0}}
2
{-1/2, 1, 0, 0}
-1/2 (-1 + x) x (-1 + y) y + (-1 + x) x^2 (-1 + y) y
```

```mathematica
"esboço da autofunção obtida"
Plot3D[ϕ[x, y], {x, 0, a}, {y, 0, b}]
```

<p><img src="figuras/metodo_Galerkin_retangular2-Polinomios_01.png" width="340"></p>

```mathematica
"curvas de nível da autofunção"
ContourPlot[ϕ[x, y], {x, 0, a}, {y, 0, b}]
```

<p><img src="figuras/metodo_Galerkin_retangular2-Polinomios_02.png" width="300"></p>
