# Notebooks

São os 16 notebooks originais do Mathematica 9 (2015). Ao lado de cada `.nb` há um `.md` com a versão para leitura: o código transcrito e os gráficos redesenhados a partir dos dados salvos no próprio notebook. Os dois são do mesmo cálculo, e o `.nb` é a fonte.

Os notebooks seguem o mesmo roteiro: definem a região e a base, montam a matriz, acham os autovalores e desenham uma autofunção (superfície, curvas de nível e linhas nodais). Cada célula começa com uma string que diz o que ela faz.

## Relatório final da iniciação científica (2015)

Os códigos citados no capítulo 2 do [relatório final](../docs/relatorio_final_2015.pdf), na ordem em que aparecem no texto.

| Notebook | O que faz |
|---|---|
| [`bilhar_retangular`](relatorio_final_2015/bilhar_retangular.md) | Solução exata do bilhar retangular (produtos de senos): superfície e curvas de nível das seis primeiras autofunções |
| [`bilhar_circular`](relatorio_final_2015/bilhar_circular.md) | Solução exata do bilhar circular (funções de Bessel e seus zeros): superfície, curvas de nível e linhas nodais das seis primeiras autofunções |
| [`metodo_Galerkin_retangular-Polinomios`](relatorio_final_2015/metodo_Galerkin_retangular-Polinomios.md) | Teste do método de Galerkin no quadrado de lado 1, com quatro polinômios que se anulam na borda: k = 2√5, 2√13 (duplo) e 2√21, contra os exatos π√2, π√5 e π√8 |
| [`metodo_Galerkin_retangular2-Polinomios`](relatorio_final_2015/metodo_Galerkin_retangular2-Polinomios.md) | O mesmo teste, com a matriz montada numa só tabela |
| [`metodo_Galerkin_retangular3-Senos`](relatorio_final_2015/metodo_Galerkin_retangular3-Senos.md) | Galerkin no quadrado com quatro senos: reproduz os autovalores exatos |
| [`metodo_Galerkin_retangular4-Senos`](relatorio_final_2015/metodo_Galerkin_retangular4-Senos.md) | O mesmo, com integração numérica (`NIntegrate`) no lugar da simbólica |
| [`metodo_expansao_circular`](relatorio_final_2015/metodo_expansao_circular.md) | Teste do método da expansão em estados estacionários: o círculo de raio 1 dentro de um quadrado de lado 2, com barreira de potencial fora dele e 100 funções de base |
| [`metodo_Galerkin_Bunimovich-Polinomios`](relatorio_final_2015/metodo_Galerkin_Bunimovich-Polinomios.md) | Galerkin no estádio de Bunimovich (a = b = 1) com nove polinômios: os nove primeiros autovalores, uma autofunção e as curvas de nível das nove |
| [`metodo_Galerkin_Bunimovich2-Senos`](relatorio_final_2015/metodo_Galerkin_Bunimovich2-Senos.md) | Galerkin no estádio com nove senos adaptados à forma: autovalores menores, ou seja, mais precisos |
| [`metodo_Galerkin_Bunimovich3-Polinomios`](relatorio_final_2015/metodo_Galerkin_Bunimovich3-Polinomios.md) | A base polinomial de novo, com integração numérica de alta precisão |
| [`metodo_expansao_Bunimovich`](relatorio_final_2015/metodo_expansao_Bunimovich.md) | Método da expansão no estádio: as nove primeiras autofunções em ordem crescente de autovalor, para comparar com o Galerkin |
| [`metodo_expansao_Sinai`](relatorio_final_2015/metodo_expansao_Sinai.md) | Método da expansão num quarto do bilhar de Sinai: autofunções, curvas de nível e linhas nodais |

## Monografia (2015)

Os códigos da [monografia](../docs/monografia_2015.pdf) "Sistemas Físicos Caóticos".

| Notebook | O que faz |
|---|---|
| [`equacao_logistica`](monografia_2015/equacao_logistica.md) | Mapa logístico: equilíbrios de período n e sua estabilidade, em forma simbólica. Para n = 2, eles são estáveis para 3 < r < 1 + √6 |
| [`equacao_logistica2`](monografia_2015/equacao_logistica2.md) | A equação logística contínua (r = 4): solução exata e expoente de Lyapunov igual a −4, negativo, ou seja, sem caos |
| [`metodo_Galerkin_Bunimovich2-Senos`](monografia_2015/metodo_Galerkin_Bunimovich2-Senos.md) | Galerkin no estádio com a base de senos, na versão usada na monografia: os nove autovalores e as curvas de nível da primeira autofunção |
| [`metodo_Galerkin_Bunimovich2-Senos2`](monografia_2015/metodo_Galerkin_Bunimovich2-Senos2.md) | O mesmo código numa só célula, sem as saídas |

## Sobre as versões para leitura

- Foram geradas em 2026 sem o Mathematica: o código das células de entrada foi transcrito para a sintaxe de texto do Mathematica. Frações, raízes e integrais viram `/`, `Sqrt[...]` e `Integrate[...]`.
- Os gráficos foram redesenhados em Python a partir dos pontos e polígonos que o notebook guarda. Cores, iluminação e eixos podem diferir um pouco do original. Nos gráficos 3D, a malha sobre a superfície foi omitida.
- Saídas muito longas foram encurtadas, e os avisos do Mathematica foram omitidos.
