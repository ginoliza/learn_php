+++
archetype = "chapter"
title = "23. Hashing"
weight = 23
+++

Transformación de datos sensibles (password) en letras, números y/o símbolos mediante un proceso matemático (similar a encripción). Oculta los datos originales de terceros.

## Convertir a hash
La función `password_hash` permite convertir texto plano en un hash. 

El primer parámetro es un texto plano, el segundo es el algoritmo de hashing.

{{< highlight type="phtml" wrap="true" hl_lines="4">}}
<?php
$password_plain = "ginoliza";

$hashed_password = password_hash($password_plain, PASSWORD_DEFAULT);

echo "$password_plain : $hashed_password <br>";
?>
{{< /highlight >}}

## Verificar/comparar
La función `password_verify` permite comparar si el password en texto plano y el password hasheado coinciden. 

El primer parámetro es un texto plano a comparar, el segundo es el password hasheado a comparar.

{{< highlight  type="phtml" wrap="true" hl_lines="2">}}
<?php
if (password_verify("ginoLIZA", $hashed_password)) {
    echo "Es correcto<br>";
} else {
    echo "Es incorrecto<br>";
} // Es incorrecto
?>
{{< /highlight >}}