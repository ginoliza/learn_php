+++
archetype = "chapter"
title = "If, else, elseif"
weight = 6
+++

## If 

{{< highlight  type="php" wrap="true">}}
$age = 21;

if ($age >= 18){
    echo "You may enter";
}

else{
    echo "You must be 18+ to enter";
}
{{< /highlight >}}

## If else
Se ejecuta la primera condición `if`o `elseif` que cumpla
{{< highlight  type="php" wrap="true">}}
$age = $_POST["age"];

if ($age >= 21){
    echo "You may enter and drink";
}

elseif($age >=18){
    echo "You may enter but not drink";
}

else{
    echo "You must be 18+ to enter";
}
{{< /highlight >}}