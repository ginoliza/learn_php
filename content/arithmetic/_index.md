+++
archetype = "chapter"
title = "03. Aritmética"
weight = 3
+++

## Operadores aritmeticos
{{< highlight type="php" wrap="true">}}
$x = 10;
$y = 2;
{{< /highlight >}}

- Suma
{{< highlight type="php" wrap="true">}}
echo $x + $y;
{{< /highlight >}}
- Resta
{{< highlight type="php" wrap="true">}}
echo $x - $y;
{{< /highlight >}}
- Multiplicación
{{< highlight type="php" wrap="true">}}
echo $x * $y;
{{< /highlight >}}
- División
{{< highlight type="php" wrap="true">}}
echo $x / $y;
{{< /highlight >}}
- Potencia
{{< highlight type="php" wrap="true">}}
echo $x ** $y;
{{< /highlight >}}
- Módulo (resto)
{{< highlight type="php" wrap="true">}}
echo $x % $y;
{{< /highlight >}}

## Operadores de incremento / decremento

- Incremento
{{< highlight type="php" wrap="true">}}
$x = 0;
$x = $x + 1; // 1

// Abreviando
$x = 0;
$x++; // 1

{{< /highlight >}}

- Decremento
{{< highlight type="php" wrap="true">}}
$x = 0;
$x = $x - 1; // -1

// Abreviando
$x = 0;
$x--; // -1

{{< /highlight >}}

- Incrementar o decrementar por un valor especifico
{{< highlight type="php" wrap="true">}}
$x = 0;
$x += 3; // 3

{{< /highlight >}}

## Precedencia de operadores
Primero parentesis, luego potencia, etc
1. `()`
2. `**`
3. `* / %`
4. `+ -`