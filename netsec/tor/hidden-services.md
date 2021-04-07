# Hidden Services

Habiendo entendido lo que es el **onion routing** los hidden services son aquellos que se encuentran directamente dentro de tor, no usan el routing de tor para llegar a ellos de forma anonima sino que estan dentro de ese routing.

![Paint skillz](../../.gitbook/assets/imagen%20%2844%29.png)

La gracia de los hidden services es que tanto nuestra conexion con ellos como ellos mismos sean ocultos. Es decir que la verdadera ubicacion del servicio \(hablando de ip\) no sea conocida para nadie realmente.

Se tiene sumado a los puntos de routing los llamados **introduction points**. Estos son en simultaneo puntos de ruteo pero que poseen una descripcion y funcionan como el punto de acceso previo al servicio.

![](../../.gitbook/assets/imagen%20%2852%29.png)

Nota: las flechas azules ocultan los dos saltos adicionales del ruteo tor.

Ahora, un cliente luego de hacer sus dos primeros saltos hablara con un rondevu point \(el tercer salto\). El mismo se conectara con el introduction point del hidden service y luego de dos saltos llegara al servicio. Un monton de saltos, muy anonimo. Ahora para comunicarse con el servicio manda una llave \(en este caso cookie\), el servicio puede aceptarla o ignorarla por completo dependiendo de la misma.Esa palabra puede ser un codigo de autentificacion.

![](../../.gitbook/assets/imagen%20%2851%29.png)

Finalmente si se decide aceptar se entabla una conexion en base al Rp y el servicio habla con el cliente atravez del mismo. Es sumamente lento pero sumamente anonimo.

![](../../.gitbook/assets/imagen%20%2836%29.png)

Hidden services como el de Facebook eliminan algunos de estos saltos ya que "sabemos donde estan los servidores de facebook" por lo que no es necesario ocultarlos y existen como forma de aumentar el anonimato del cliente.

















