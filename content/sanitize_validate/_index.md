+++
archetype = "chapter"
title = "18. Sanitize & validate"
weight = 18
+++

Se puede insertar codigo malicioso si no se desinfecta o valida, si ingresamos el siguiente codigo javascript en algun campo:
```js
<script>alert("Tienes 10 virus!");</script>
```
De la pagina web:
```html
<form action="index.php" method="post">
    <label>Name:</label><br>
    <input type="text" name="name"><br>

    <label>Age:</label><br>
    <input type="text" name="age"><br>

    <label>Email:</label><br>
    <input type="text" name="email"><br>

    <input type="submit" name="submit" value="Submit">
</form>
```

```php
$name = $_POST["name"];
echo "$name";

$age = $_POST["age"];
echo "$age";

$email = $_POST["email"];
echo "$email";
```

Se ejecutará codigo **javascript** ya que se está inyectando directamente en la página.

Para preveer eso, se usa se usa la función `filter_input()`

## Sanitize
Limpia la data de un _input_ al eliminar o escapa ciertos caracteres peligrosos

### FILTER_SANITIZE_SPECIAL_CHARS
```php
$name = filter_input(
    INPUT_POST, 
    "name",
    FILTER_SANITIZE_SPECIAL_CHARS
    );
echo "Name: $name <br>"; 
// <script>alert("Tienes 10 virus!");</script>
```
### FILTER_SANITIZE_NUMBER_INT
```php
$age = filter_input(
    INPUT_POST,
    "age",
    FILTER_SANITIZE_NUMBER_INT
);
echo "Age: $age <br>";
// 10
```
### FILTER_SANITIZE_EMAIL
```php
$email = filter_input(
    INPUT_POST,
    "email",
    FILTER_SANITIZE_EMAIL
);
echo "Email: $email";
// scriptalertTienes10virus!script
```

## Validate
Se asegura que la data de un _input_ esté en el formato correcto y esperado. En caso contrario, no lo toma.

### FILTER_VALIDATE_INT
```php
$age = filter_input(
    INPUT_POST,
    "age",
    FILTER_VALIDATE_INT
);
echo "Age: $age <br>";
// a12 => 
// 12 => 12
```

### FILTER_VALIDATE_EMAIL
```php
$email = filter_input(
    INPUT_POST,
    "email",
    FILTER_VALIDATE_EMAIL
);
echo "Email: $email";
// correofoo => 
// a@b.c => a@b.c
```