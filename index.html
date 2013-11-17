<!DOCTYPE html>
<html>
<head>
<meta content="text/html; charset=UTF-8" http-equiv="content-type">
<style>
body {
        font-family:Courier New;
        font-size:12px;
}
</style>
<script>

// CharCode Class
var CharCode = function(string) {
    this.codeArray = [];
    for(var i = 0, length = string.length; i < length; i++) {
        this.codeArray.push(this.getCharCode(string[i]));
    }
}
CharCode.prototype.getCharCode = function(char) {
    return char.charCodeAt(0);
}

// Check Character
function checkOperator(operator) {
    var operators = ['+','-','*','/'];
    if(operators.indexOf(operator) > -1) {
        return true
    } else {
        return false;
    }
}
    

// GENE Class
var Gene = function(code) {    
    this.operators  = '*/-+';
    this.code       = '';
    this.cost       = 0;
    if(code) this.code = code;
}
Gene.prototype.checkOperator = function(char) {
    for(var i = 0, length = this.operators.length; i < length; i++) {
        if(this.operators[i] === char) {
            return true
        }
    }
    return false
}
Gene.prototype.random = function(allowedChars) {
    var max     = allowedChars.length - 1;
    var min     = 0; 
    var length  = allowedChars.length/2;
    while(length--) {
        var randomPos  = Math.floor(Math.random() * ( 1 + max - min )) + min;
        var randomChar = String.fromCharCode(allowedChars[randomPos]);
        if(this.code.length === 0) {
            this.code += randomChar;
        }
        else if(this.code.length > 0) {

            if(this.checkOperator(randomChar) === true &&
                this.checkOperator(this.code[this.code.length - 1]) === false              
            ) {
                this.code += randomChar;
            }

            if(this.checkOperator(randomChar) === false) {
                this.code += randomChar;
            }
        }
    }
}
Gene.prototype.crossover = function(gene) {
    var pivot   = Math.round(this.code.length / 2) - 1;

    if(this.checkOperator(this.code[pivot - 1]) === true &&
        this.checkOperator(gene.code[pivot]) === true
        ) {
        var child1  = this.code.substr(0,pivot - 1) + this.code[pivot - 1] + '0' + gene.code.substr(pivot + 1);
    }
    else {
        var child1  = this.code.substr(0,pivot) + gene.code.substr(pivot);
    }

    if(this.checkOperator(gene.code[pivot + 1]) === true &&
        this.checkOperator(this.code[pivot]) === true
        ) {
        var child2  = gene.code.substr(0,pivot - 1) + gene.code[pivot - 1] + '0' + this.code.substr(pivot + 1);
    }
    else {
        var child2  = gene.code.substr(0,pivot) + this.code.substr(pivot);
    }

    console.log(child1);
    console.log(child2);
    return [new Gene(child1),new Gene(child2)]
}
Gene.prototype.mutate = function(chance,allowedChars) {
    if(Math.random() > chance) return;
    var index       = Math.floor(Math.random() * this.code.length);
    var upOrDown    = Math.random() <= chance ? -1 : 1;
    var randomPos   = Math.floor(Math.random() * allowedChars.length);
    
    if(randomPos === 0 && upOrDown === -1 ||
        randomPos === (allowedChars.length - 1) && upOrDown === 1
    ) {
        randomPos = randomPos;
    }
    else {
        randomPos = randomPos + upOrDown;
    }

    var newChar     = String.fromCharCode(allowedChars[randomPos]);
    var newString   = '';

    for(var i = 0; i < this.code.length; i++) {
        if(i === index) {
            if((this.checkOperator(newChar) === true && 
                this.checkOperator(this.code[index - 1]) === true) || 
                (this.checkOperator(newChar) === true && 
                this.checkOperator(this.code[index + 1]) === true )
            ) {
                newString += this.code[i];
            }
            else {
                newString += newChar;
            }
        }
        else {
            newString += this.code[i];
        } 
    }
   console.log(newChar);
    console.log(this.code);
    this.code = newString;
    console.log(this.code);
}
Gene.prototype.calcCost = function(goal) {
    this.sanitize();

   /* try {
        eval(this.code);
    }
    catch (e) {
        if(e instanceof SyntaxError) {
            this.cost = 10000;
            return false;
        }
    }*/

    this.cost = goal - eval(this.code);
}

Gene.prototype.sanitize = function() {
    var length = this.code.length;

    for(var i = 0; i < length; i++) {

        if(checkOperator(this.code[length - 1]) === true) {
            this.code = this.code.substring(0,length-1) + this.code.substring(length + 1, this.code.length);
        }
        if(this.code[0] === '/' || this.code[0] === '*') {
            this.code = this.code.substring(0,0) + this.code.substring(1, this.code.length);
        }
        if(checkOperator(this.code[i]) === true && checkOperator(this.code[i+1] === true)) {
            this.code = this.code.substring(0,i) + this.code.substring(i + 1, this.code.length);
        }
        if(checkOperator(this.code[i]) === true && checkOperator(this.code[i-1] === true)) {
            this.code = this.code.substring(0,i) + this.code.substring(i + 1, this.code.length);
        }
    }
}

// Population
var Population = function(goal,size,allowedString) {
    this.members          = [];
    this.goal             = goal
    this.generationNumber = 0;   

    var charCode          = new CharCode(allowedString);
    this.allowedChars     = charCode.codeArray;

    while(size--) {
        var gene = new Gene();
        gene.random(this.allowedChars);
        this.members.push(gene);
    }
}
Population.prototype.display = function() {
    document.body.innerHTML = '';
    document.body.innerHTML += ("<h2>Generation: " + this.generationNumber + "</h2>");
    document.body.innerHTML += ("<ul>");
    for (var i = 0; i < this.members.length; i++) {
        document.body.innerHTML += ("<li>" + this.members[i].code + " (" + this.members[i].cost + ")");
    }
    document.body.innerHTML += ("</ul>");
}
Population.prototype.sort = function() {
    this.members.sort(function(a, b) {
        return a.cost - b.cost;
    });
}
Population.prototype.generation = function() {
    for(var i = 0; i < this.members.length; i++) {
        this.members[i].calcCost(this.goal);
    }

    this.sort();
    this.display();
    var children = this.members[0].crossover(this.members[1]);
    this.members.splice(this.members.length - 2, 2, children[0], children[1]);

    for (var i = 0; i < this.members.length; i++) {
        this.members[i].mutate(0.5,this.allowedChars);
        this.members[i].calcCost(this.goal);
        if (parseFloat(this.members[i].cost) === 0) {
            this.sort();
            this.display();
            alert('fsef');
            return true;
        }
    }
    this.generationNumber++;
    var scope = this;
    setTimeout(function() {
        scope.generation();
    }, 20);

}
  

window.onload = function() {
    population = new Population(15, 6, '1234567890+-*/');
    population.generation();
}



</script>
</head>
<body>
<p></p>
</body>
</html>


</head>
<body>
<p></p>
</body>
</html>
