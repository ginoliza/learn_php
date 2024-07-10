+++
archetype = "chapter"
title = "Bucle for"
weight = 9
+++

Repetir código cierto numero de veces

{{< highlight  type="php" wrap="true">}}
for ($x = 1; $x <= 10; $x++) {
    echo "{$x} <br>";
}
{{< /highlight >}}

Ejemplo - contar desde 1 hasta algún número
{{< highlight type="php" wrap="true">}}
$counter = $_POST["counter"];
for ($i = 1; $i <= $counter; $i++) {
    echo $i . "<br>";
}
{{< /highlight >}}