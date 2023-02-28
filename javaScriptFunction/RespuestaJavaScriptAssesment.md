# Evaluaci�n JavaScript

Analiza el siguiente c�digo y responde a las preguntas:

```

(function() {
    var User = function(name, age){
        this.name = name;
        this.age = age;  
    };  

    User.prototype.welcome = function(){
        console.log('Welcome ' + this.name);  
	};  

    User.prototype.getAge = function(){
        return this.age;  
    };
    
    console.log(VipUser);
    console.log(DummyUser);  


    function DummyUser(name, surname) {
        this.name = name;
        this.surname = surname;  

        this.toString = function() {
            return this.name + ' ' + this.surname;  
		}  

    }  

    DummyUser.prototype.toString2 = function() {
        return this.name + ' ' + this.surname;  
    }

    var VipUser = function (name, age, memberId) {

        User.call(this, name, age);

        this.myMemberId=function()
        {
            console.log(memberId);
        }
    };

    VipUser.prototype = new User;


}());  
```

1. �Cu�les pueden ser las razones para incluir todo el c�digo en una funci�n?

El resumen es incluirlo todo en el código en una función puede ayudar a mejorar los conflictos de nombres, organizacion del codigo, prevencion de errores, modularidad y reutilizacion.

2. �Por qu� las l�neas `console.log(VipUser);` y `console.log(DummyUser);` no generan un error?

Las líneas console.log(VipUser); y console.log(DummyUser); no generan un error porque JavaScript permite acceder a una variable o función antes de que se hayan definido.
VipUser y DummyUser son funciones constructoras que se definen más adelante en el código.

�Por qu� no muestran las dos el valor `undefined` si se ejecuta el c�digo en un navegador?

En algunos navegadores o entornos de ejecución, las líneas console.log(VipUser); y console.log(DummyUser); no muestran el valor 'undefined' cuando se ejecuta el código debido a diferencias en la implementación de JavaScript.
Estas líneas se ejecutan antes de que se definan las funciones constructoras VipUser y DummyUser, lo que significa que en teoría deberían imprimir undefined en la consola.

Es importante tener en cuenta este comportamiento cuando se escribe código en JavaScript y seguir las mejores prácticas de programación para evitar problemas de hoisting.

3. Los m�todos `toString` y `toString2` est�n definidos de forma diferente en `DummyUser`.
�Qu� diferencia hay entre declararlos de una manera u otra?

En DummyUser, el método toString está definido como una función anónima que se asigna directamente a la propiedad toString del objeto, mientras que el método toString2 se define en el prototipo de DummyUser utilizando la sintaxis de la propiedad de una función.

La principal diferencia entre definir métodos como propiedades del objeto o en el prototipo del objeto es cómo se almacena y se comparte la función en la memoria. 

Si el método es específico de cada instancia del objeto, puede ser apropiado definirlo como una propiedad del objeto. Sin embargo, si el método se comparte entre todas las instancias del objeto, es más eficiente definirlo en el prototipo del objeto.