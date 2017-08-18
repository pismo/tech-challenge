# Cores no formato RGB

O RGB é um sistema que permite representar cores a partir da combinação dos componentes
R (vermelho), G (verde) e B (azul). Uma cor RGB pode ser escrita em formato hexadecimal
ou como um vetor de 3 componentes. Por exemplo, a cor vermelha pode ser representada da
seguinte forma:
```
/-------------+-----+-----+-----\
|             | R   | G   | B   |
+-------------+-----+-----+-----+
| Hexadecimal | FF  | 00  | 00  |
+-------------+-----+-----+-----+
| Vetor       | 255 | 0   | 0   |
\-------------+-----+-----+-----/
```
A representação da tela do computador na memória é a de uma matriz de pontos onde  cada
ponto contém uma cor. Dependendo das configurações gráficas cada cor pode  conter,  por
exemplo,  16,  24  ou  32  bits.  Para  representar  os componentes R, G e B em 16 bits
utilizamos 5 bits para o vermelho, 6 bits para o verde e 5 bits para o azul. Para  esta
representação damos o nome de RGB565.

Para  o  formato  de  32  bits  utilizamos  8  bits  para  cada  componente.  Para esta
representação damos o nome de RGB888. Segue o exemplo da cor amarela nos dois formatos:

### RGB888:
```
/---------+-------------+-------------+-------------\
|         |   8 bits    |   8 bits    |   8 bits    |
+---------+------+------+------+------+------+------+
| Hexa    |   F  |   F  |   F  |   F  |   0  |   0  |
+---------+------+------+------+------+------+------+
| Binário | 1111   1111 | 1111   1111 | 0000   0000 |
+---------+-------------+-------------+-------------+
| Decimal |     255     |     255     |      0      |
\---------+-------------+-------------+-------------/
```
### RGB565:
```
/---------+----------+-----------+----------\
|         |   5 bits |  6 bits   |  5 bits  |
+---------+------+---+-----+-----+---+------+
| Hexa    |   F  |    F    |    E    |   0  |
+---------+------+---+-----+-----+---+------+
| Binário | 1111   1 | 111   111 | 0   0000 |
+---------+----------+-----------+----------+
| Decimal |    31    |    63     |     0    |
\---------+----------+-----------+----------/
```
Escreva  um programa que receba na primeira linha o formato desejado (RGB888 ou RGB565)
e  na  linha  seguinte  um  valor  hexadecimal ou um vetor RGB. Os valores hexadecimais
devem  começar  por  0x  e  os  vetores  são  3  valores inteiros separados por espaço.
O programa deve converter de hexa para vetor quando a entrada for hexa, e de vetor para
hexa quando a entrada for vetor. Veja o exemplo:
```
Entrada:
RGB888
0xFFFFFF

Saida:
255 255 255

Entrada:
RGB888
255 255 255

Saída:
0xFFFFFF
```
Para  o  formato  RGB888  cada componente (R, G e B) varia entre 0 e 2ˆ8. Já no formato
RGB565  os  limites são, 0 <= R <= 2^5, 0 <= G <= 2^6 e 0 <= B <= 2^5. Não é necessário
validar  os  limites  na  entrada,  mas  os  valores  devem ser truncados para caber na
representação.
