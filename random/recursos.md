# Recursos

{% embed url="https://techlore.tech/resources.html" %}

```javascript
Código de ejemplo
//
// Pipeline class example
//
class Pipeline {
constructor () {
// Initialize attributes
}
use ( filter ) {
// Add a filter to the execution flow
}
run ( input ) {
/* Execute the first filter and then pass the modified input
to the next filter
*/
}
}
//
// Pipeline execution example
//
var pipeline = new Pipeline ();
var filterMultiply = ( input , next ) => {
let result = input * input ;
next ( null , result );
};
var filterPrint = ( input , next ) => {
console . log ( `Result from filter is ${ input } ` );
next ( null , input );
};
pipeline . use ( filterMultiply );
pipeline . use ( filterPrint );
pipeline . run ( 5 );
pipeline . run ( 10 );
pipeline . run ( 15 );
```

