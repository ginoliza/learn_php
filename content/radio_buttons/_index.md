+++
archetype = "chapter"
title = "14. Botones de radio"
weight = 14
+++

El `name` debe ser uno para todo el grupo, sino se podrán seleccionar todos.

```html
<form action="index.php" method="post">
    Género <br>
    <input type="radio" name="gender" value="Masculino">
    <label>Masculino</label><br>
    <input type="radio" name="gender" value="Femenino">
    <label>Femenino</label><br>    

    <input type="submit" name="submit" value="Submit">
</form>
```

```php
if(isset($_POST["submit"])){
    if(isset($_POST["gender"])){
        $gender = $_POST["gender"];
        echo $gender;
    }
}
```

## Ejercicio
Seleccionar una de 3 tarjetas e imprimirla.

{{% expand title="Solución" %}}
```phtml
<form action="index.php" method="post">
    <input type="radio" name="credit_card" value="visa">
    <label>Visa</label><br>
    
    <input type="radio" name="credit_card" value="mastercard">
    <label>Mastercard</label><br>
    
    <input type="radio" name="credit_card" value="amex">
    <label>American Express</label><br>

    <input type="submit" name="submit" value="Submit">
</form>
</html>

<?php
if(isset($_POST["submit"])){
    // si credit_card ha sido establecida
    if(isset($_POST["credit_card"])){        
        $credit_card = $_POST["credit_card"];
        echo "Tajeta seleccionada: $credit_card";
    }
    // si no
    else{
        echo "Por favor seleccione una tarjeta";
    }
}
?>
```
{{% /expand %}}