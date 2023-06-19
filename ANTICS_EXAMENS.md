# EC: Estructura de Computadors (material professor R. Tous)

## Preguntes famoses d'antics examens 

S'ha creat una entrada a Atenea per que pugueu realitzar el lliurament dels problemes.

## Pregunta 5 final 22-23/Q1

Aquí la polèmica va ser la solució del valor de "e" a l'apartat (b). La solució publicada era errònea, la correcta seria 0x0789.

![image](antics_examens/22_23_Q1_final_p5.png)

## Pregunta 7 final 20-21/Q1

Aquí la polèmica va ser la solució oficial de l'apartat (d), que era errònea:

penalització accés instrució =tp_i= tbloc + thit = 18 + 2 = 20 cicles
penalització accés a dades = tp_d = (1-pm) *  (tbloc + thit) + pm * (2tbloc + thit) = 2/3 * 20 + 1/3 * 38 = 26 cicles

b) penalització fetch = 0,05 * tp_i = 0,05 * 20 = 1
c) penalització lectura/escriptura dada = 0,15 * 0,3 * tp_d = 0,15 * 0,3 * 26 = 1,17 = 1,2

La solució correcta de l'apartat (d) seria:

d) CPI = CPIideal + penalització fetch + penalització dades = 2,5 + 1 + 1,2 = 4,7 cicles

![image](antics_examens/20_21_Q1_final_p7.png)




