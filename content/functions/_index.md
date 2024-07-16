+++
archetype = "chapter"
title = "16. Funciones"
weight = 16
+++

Empieza con la palabra `function` seguido de su nombre y entre parentesis sus parámetros, puede retornar algun valor. 

Se usa llamando a la función en algun otro lado del código. 

```php
function isEven($num){
    if($num % 2 == 0){
        echo "$num es par";
    }else{
        echo "$num es impar";
    }
}

isEven(2); 
isEven(5);
```

Se puede forzar que los parámetros tengan algún tipo en particular

{{< highlight  type="php" wrap="true" lineNos="true" hl_lines="1">}}
function isEven(int $num){
...
{{< /highlight >}}

## Ejercicio
Crear una funcion `datos` que tome `nombre` de tipo string y `edad` de tipo entero e imprima los datos. 

{{% expand %}}
```php
function datos(string $name, int $age){
    echo "Nombre: $name <br>Edad: $age";
}

datos("carlos", 20);
```
{{% /expand %}}