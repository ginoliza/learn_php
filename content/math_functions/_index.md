+++
archetype = "chapter"
title = "05. Funciones Matemáticas"
weight = 5
+++

- abs: valor absoluto
- round: redondear, se puede especificar cuandos decimales
- floor: redondear para abajo
- ceil: redondear para arriba
- pow: potencia
- sqrt: raiz cuadrada
- max: maximo valor
- min: minimo valor
- pi: 3.14159....
- rand: random

Ejercicio: dado el radio de un círculo, calcular la circunferencia, area y volumen

{{% expand title="Solución" %}}
```php
<body>
    <form action="index.php" method="post">
    <h1>Círculo</h1>    
    <label for="">Radio</label><br>
    <input type="text" name="radio" id="">
    <input type="submit" value="Calcular">
    </form>
</body>
</html>
<?php
    $radio = $_POST["radio"];
    $C = round(2*pi()*$radio, 2);
    $A = round(pi()*pow($radio, 2), 2);
    $V = round((4/3)*pi()*pow($radio, 3), 2);
    echo "r: {$radio} <br>";
    echo "C: {$C} <br>";
    echo "A: {$A} <br>";
    echo "V: {$V} <br>";
?>
```
{{% /expand %}}