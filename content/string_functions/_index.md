+++
archetype = "chapter"
title = "Funciones de string"
weight = 17
+++

## strlen
Tamaño del string
```php
echo strlen("Gino Liza"); // 9
```
## strtolower
Convierte el string a minúscula
```php
echo strtolower("Gino Liza"); // gino liza
```
## strtoupper
Convierte el string a mayúscula
```php
echo strtoupper("Gino Liza"); // GINO LIZA
```
## trim
Elimina espacios delante y detras del string. Se puede especificar el caracter. 
```php
echo trim("   Gino Liza  "); // Gino Liza
echo trim("--Gino Liza---", "-"); // Gino Liza
```
## str_pad
Rellena un string hasta el número de caracteres con un caracter
```php
echo str_pad("Gino Liza", 12, "X") // Agrega el tercer parametro al espacio faltante
```
## str_replace
Reemplaza un caracter por otro dentro de un string
```php
echo str_replace("i", "|", "Gino Liza"); // G|no L|za
```
## strrev
Invierte un string
```php
echo strrev("Gino Liza"); // aziL oniG
```
## str_shuffle
Barajea un string
```php
echo str_shuffle("Gino Liza"); // aleatorio
```
## strcmp
Compara un string, si es diferente 1, si es igual 0
```php
echo strcmp("Gino Liza", "Gino LIZA");
```
## substr
Crea un string a partir del primer parámetro
```php
echo substr("Gino Liza", 0, 4); // Gino
echo substr("Gino Liza", 4); // Liza
```
## explode
Rompe un string en piezas por un separador
```php
$arr = explode(" ", "Gino Liza"); // {"Gino", "Liza"}

foreach($arr as $name){
    echo $name . "<br>";
}
```
## implode
Convierte un array a un string. Se puede especificar un separador
```php
$arr = array("Gino", "Liza");
echo implode($arr) . "<br>"; // GinoLiza
echo implode(" ", $arr) . "<br>"; // Gino Liza
```