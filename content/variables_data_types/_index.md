+++
archetype = "chapter"
title = "02. Variables y Tipos de Datos"
weight = 2
+++

## Tipos
- string 
{{< highlight type="php">}}
$name = "Gino";

// variable dentro de strings
echo "Hello, I'm {$name}<br>";

{{< /highlight >}}
- entero
{{< highlight type="php">}}
$age = 30;
echo "I'm {$age} years old<br>";
{{< /highlight >}}
- flotante
{{< highlight type="php">}}
$price = 4.99;
// Para escapar el $ se usa \
echo "My gpa is \${$price} <br>";
{{< /highlight >}}
- booleano 
{{< highlight type="php">}}
$employed = 1;
echo "I am currently {$employed}";

// En caso el booleano sea false, no se mostrará en el navegador. Si es true se muestra 1
{{< /highlight >}}

