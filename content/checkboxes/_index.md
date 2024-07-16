+++
archetype = "chapter"
title = "15. Checkboxes"
weight = 15
+++

## Por separado

Ejemplo - para seleccionar si nos gusta pizza, pollo o hamburguesa e imprimirlo. Los `key` y `value` que recibe `php` son los `name` y `value` del `html`.

```phtml
...html
<form action="index.php" method="post">
    <input type="checkbox" name="pizza" value="Pizza">
    Pizza <br>
    <input type="checkbox" name="pollo" value="Pollo">
    Pollo <br>
    <input type="checkbox" name="hamburguesa" value="Hamburguesa">
    Hamburguesa <br>
    <input type="submit" name="submit" value="Submit">    
</form>
</html>

<?php
if(isset($_POST["pizza"])){    
    echo "You like pizza <br>";
}else{
    echo "You DONT like pizza <br>";
}

if(isset($_POST["pollo"])){    
    echo "You like pollo <br>";
}else{
    echo "You DONT like pollo <br>";
}

if(isset($_POST["hamburguesa"])){    
    echo "You like hamburguesa <br>";
}else{
    echo "You DONT like hamburguesa <br>";
}
?>
```

## Juntos en un array

El `name` em el `html` debe ser el mismo para todos los checkboxes seguido de corchetes `[]`. Esto hace que sea un array

```phtml
...html
<form action="index.php" method="post">
    <input type="checkbox" name="comidas[]" value="Pizza">
    Pizza <br>
    <input type="checkbox" name="comidas[]" value="Pollo">
    Pollo <br>
    <input type="checkbox" name="comidas[]" value="Hamburguesa">
    Hamburguesa <br>
    <input type="submit" name="submit" value="Submit">    
</form>
</html>

<?php
$comidas = $_POST["comidas"];

foreach($comidas as $comida){
    echo "You like $comida <br>";
}
?>
```