# DEEP JS.

* **Track:** _Common Core_
* **Alumna:** _Yosseline Apcho Huaman._

***
## OBJETIVO:

- Profundizar y comprender los temas vistos en clase, por medio de una comprensión del archivo js ubicado en este repositorio.

***
## ¿QUÉ SON LAS FUNCIONES EN JAVASCRIPT?

- Son subprogramas, que se componen de una secuencia de declaraciones.
- Toda función en JavaScript es un objeto Function.

***

## GLOBAL FUNCTIONS:

- Son aquellas funciones que no están ubicadas dentro de otra función.
- **Funciones globales en app.js:** Si revisamos bien el código, notamos que la única función global sería:

```js
$(document).ready(function(){
  ...
});
```

## LOCAL FUNCTIONS:

- Son aquellas funciones que están dentro de otra función.
- **Funciones locales en app.js** : Como vimos, solo hay una función global. Y por ende, las demás funciones serían locales.

```js
// Identifica el evento que nos permite capturar el input del usuario
$inputCard.on('input', function() {
  isValidCreditCard($(this).val().trim());
});

// Función que habilita el boton del formulario
function activeButton() {
  $buttonNext.attr('disabled', false);
}

// Funcion que desabilita el boton del formulario
function desactiveButton() {  
  $buttonNext.attr('disabled', true);
}

// Funcion que valida la longitud del input ingresado por el usuario
function longitud(input) {
  if (input.trim().length === 16) {
    return input;
  }
}

// Funcion que valida la longitud del input ingresado por el usuario
function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}

// Funcion que valida que sea una un numero de tarjeta valido   
function isValidCreditCard(numberCard) {
  var creditCardNumber = soloNumeros(longitud(numberCard));
  if (creditCardNumber !== undefined) {
    ...
  } else {
    ...
  }
}
```

## CALLBACK FUNCTIONS:

- Como su nombre lo indica, es una “llamada de vuelta”.
- Es una función que es enviada a otra función como parámetro, esperando que la función que la llame se encargue de ejecutar esa función callback.
- **Funciones de callback en app.js** :

```js
$(document).ready(function() {
  ...
});

// Identifica el evento que nos permite capturar el input del usuario
$inputCard.on('input', function() {
  isValidCreditCard($(this).val().trim());
});
```

## EXPRESSION FUNCTIONS:

- Son aquellas funciones asignadas a variables.
- **Funciones de expresión en app.js** : No se encontró ninguna función de ese tipo. Por ello, se creó un ejemplo.

```js
//anonymous function expression
var a = function() {
    return 3;
}
```

## STATEMENT FUNCTIONS:

- Son aquellas funciones que son creadas directamente, y son llamdas en cualquier parte de su scope.
- **STATEMENT FUNCTIONS en app.js**

```js
// Funcion que valida la longitud del input ingresado por el usuario
function longitud(input) {
  if (input.trim().length === 16) {
    return input;
  }
}

// Funcion que valida la longitud del input ingresado por el usuario
function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}

// Funcion que valida que sea una un numero de tarjeta valido   
function isValidCreditCard(numberCard) {
  var creditCardNumber = soloNumeros(longitud(numberCard));
  if (creditCardNumber !== undefined) {
    ...
  } else {
    console.log('Verifique el numero de su tarjeta');
    desactiveButton();  
  }
}
```

## CLOUSURE:

- Funciones que manejan variables independientes. En otras palabras, "recuerda" el entorno en el que se ha creado.

```js
// Identificar el evento que nos permite capturar el input del usuario
$inputCard.on('input', function() {
  isValidCreditCard($(this).val().trim());
});

function isValidCreditCard(numberCard) {
  ...
}

// Funcion que valida la longitud del input ingresado por el usuario
function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}

// Funcion que valida que sea una un numero de tarjeta valido   
function isValidCreditCard(numberCard) {
  var creditCardNumber = soloNumeros(longitud(numberCard));
  if (creditCardNumber !== undefined) {
    ...
  } else {
    ...  
  }
}

// Funciones que habilita el boton del formulario
function activeButton() {
  $buttonNext.attr('disabled', false);
}

// Funcion que desabilita el boton del formulario
function desactiveButton() {  
  $buttonNext.attr('disabled', true);
}

// Funcion que valida que sea una un numero de tarjeta valido   
function isValidCreditCard(numberCard) {
  var creditCardNumber = soloNumeros(longitud(numberCard));
  if (creditCardNumber !== undefined) {
    ...

    if (sumaTotal % 10 === 0) {
      console.log('Es una tarjeta valida');
      activeButton();
    } else {
      console.log('No es un numero valido');
      desactiveButton();
    }
  } else {
    console.log('Verifique el numero de su tarjeta');
    desactiveButton();  
  }
}
```

## SCOPE:

- Es el alcance de una variable, puede ser de dos tipos, global y local. Una variable/función cuyo scope es global se puede acceder desde cualquier parte del código, una local solo desde la función que la contiene.


## Stack Execution:

- Tienen esta denominación, las funciones y variables que deberían de cargar y ejecutarse durate el contexto de ejecución, para el levantamiento de la página web.

## Event Queue:

- Son las funciones que se crean durante la fase de creación del contexto de ejecución, y que esperan en el hoisting, a ser ejecutadas por el usuario, cada vez que dicho usuario interactúe con la
