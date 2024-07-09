+++
archetype = "chapter"
title = "Operadores lógicos"
weight = 7
+++

## AND `&&` y OR `||`
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
{{< highlight  type="php" wrap="true" lineNos="true">}}
$variable = true;

if(!$variable == true){
    echo "es verdad";
}
else{
    echo "es falso";
}

{{< /highlight >}}