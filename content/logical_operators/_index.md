+++
archetype = "chapter"
title = "07. Operadores lógicos"
weight = 7
+++

## AND `&&` y OR `||`
### AND
Verdad si ambas condiciones lo son

### OR
Verdad si al menos una es verdad

Ejemplo - Para votar se requiere:
- Ser mayor de 18 años
- Ser ciudadano
{{< highlight  type="php" wrap="true">}}
$age = 18;
$ciudadano = false;

if($age >= 18 && $ciudadano == true){
    echo "Cumple ambos requisitos";
}
else if($age || $ciudadano){
    echo "Sólo cumple un requisito";
}
else{
    echo "No cummple";
}
{{< /highlight >}}
## NOT `!`
Verdad si es falso, Falso si es verdad

{{< highlight  type="php" wrap="true" lineNos="true">}}
$variable = true;

if(!$variable == true){
    echo "es verdad";
}
else{
    echo "es falso";
}

{{< /highlight >}}