# CalculadoraIMC
<!--HTML-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de IMC</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="container">
        <h1>calculadora IMC</h1>
        <div class="input">
            <label>Nome</label>
            <input id="name" type="text" placeholder="Nome">
        </div>
        <div class="input">
            <label>Altura</label>
            <input id="height" type="number" placeholder="Altura (m)">
        </div>
        <div class="input">
            <label>Peso</label>
            <input id="weight" type="number" placeholder="Peso (kg)">
        </div>
        
        <button onclick="IMC()" id="calcular">calcular</button>
        
        <div id="result"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>

<!--CSS-->

#container{
    max-width: 400px;
    height: 500px;
    margin: auto;
    background-color: rgb(255, 217, 0);
    border: 2px solid black;
    border-radius: 10px;
    margin-top: 50px;
}
h1{
    text-align: center;
}
label{
    margin-right: 50px;
    
}
.input{
    display: flex;
    float: right;
    margin-right: 50px;
    margin-top: 20px;
}
button{
    
    width: 100%;
    box-sizing: border-box;
    padding: 15px;
    
    margin-top: 40px;
}
#result{
    width: 250px;
    height: 150px;
    background-color: black;
    margin: auto;
    margin-top: 25px;
    color: rgb(255, 217, 0);
    text-align: center;
    line-height: 150px;
    border: solid;
    border-radius: 10px;
    font-weight: bold;
}

<!--JavaScript-->



var calcular = document.getElementById("calcular");


function IMC(){
    var name = document.getElementById("name").value;
    var height= document.getElementById("height").value;
    var weight = document.getElementById("weight").value;
    var result = document.getElementById("result");

    if(name == "" || height == "" || weight == ""){
        alert("preencha todos os campos!")
    }
    else{
        var imc = (weight/(height^2)).toFixed(2);
        
        if(imc<18.5){
            var i = "magreza";
        }
        else if(imc>=18.5 && imc<25){
            var i = "Peso normal";
        }
        else if(imc>=25 && imc<30){
            var i = "sobrepeso";
        }
        else if(imc>=30 && imc<40){
            var i = "obesidade"
        }
        else if (imc>=40){
            var i = "obesidade grave";
        }

        result.innerHTML = "seu imc é " + imc + ", " + i;    
    }
    
}
