# Arquitectura

## Booking

{% api-method method="post" host="https://api" path="/v1/bookings/" %}
{% api-method-summary %}
Create Booking
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="Zone" type="integer" required=true %}
Zona dentro del departamento, va del 1-99
{% endapi-method-parameter %}

{% api-method-parameter name="State" type="integer" required=true %}
Departamento donde se vacuna acorde a codificacion del pais
{% endapi-method-parameter %}

{% api-method-parameter name="Schedule" type="integer" required=true %}
Horario en el cual desea vacunarse. Valores posibles \(1 – todo el día, 2 – Matutino, 3 – Vespertino\)
{% endapi-method-parameter %}

{% api-method-parameter name="ReservationDate" type="object" required=true %}
Fecha a vacunarse por primera dosis en formato dd/mm/aaaa
{% endapi-method-parameter %}

{% api-method-parameter name="Cellphone" type="string" required=true %}
Celular de quien reserva
{% endapi-method-parameter %}

{% api-method-parameter name="DocumentId" type="string" required=true %}
El documento de identidad de la persona
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Reserva creada y procesada con exito
{% endapi-method-response-example-description %}

```
{
"id": "Codigo de reserva", 
"DocumentId": "documento de la persona",
"VaccineInfo": ["place", "date"],
"SentTimestamp" : "Timestamp asociado a la envío del mensaje por parte del frontend"
"ResponseTimestamp": "Timestamp asociado al momento de envío de la respuesta por parte del backend"
"DiffTimestamp": "Diferencia entre los timestamps de envío y respuesta."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
La reserva fue aceptada por el sistema pero no fue procesada aún.
{% endapi-method-response-example-description %}

```
{
"Id": "Codigo de reserva", 
"Message" : "Mensaje indicando que la solicitud se asignará en cuanto se asignen nuevos cupos"
"SentTimestamp" : "Timestamp asociado a la envío del mensaje por parte del frontend"
"ResponseTimestamp": "Timestamp asociado al momento de envío de la respuesta por parte del backend"
"DiffTimestamp": "Diferencia entre los timestamps de envío y respuesta."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
En caso de que algun parametro no sea valido se retorna un mensaje explicativo
{% endapi-method-response-example-description %}

```
{    "message": "parametro invalido + mensaje explicando"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api" path="/v1/bookings/:documentId" %}
{% api-method-summary %}
Get booking info
{% endapi-method-summary %}

{% api-method-description %}
Consultar dia de agendado
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="documentId" type="string" required=false %}
Documento de identidad a consultar reserva.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Informacion de reserva solicitada
{% endapi-method-response-example-description %}

```
{
"id": "Codigo de reserva", 
"VaccineInfo": ["place", "date"],
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No existe reserva asociada para ese documento
{% endapi-method-response-example-description %}

```
{
"ErrorMessage" : Mensaje explicativo de error.
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://api" path="/v1/bookings/" %}
{% api-method-summary %}
Delete booking
{% endapi-method-summary %}

{% api-method-description %}
Se elimina la reserva asociada al documento
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="bookingId" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="documentId" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Se elimina la reserva asociada
{% endapi-method-response-example-description %}

```
{
"message": Reserva {$ Código de reserva} para la Cédula de Identidad {$ Cédula de identidad} ha sido cancelada
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
En caso de no encontrar reserva asociada
{% endapi-method-response-example-description %}

```
"message" : mensaje explicando lo sucedido.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Users

{% api-method method="get" host="https://api" path="/v1/users/:id" %}
{% api-method-summary %}
Get user
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
User id
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Token identificador del usuario administrador
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
"id": "identificador unico del usuario",
"isAdmin" : "marca si es un usuario administrador"
"email": "correo del usuario"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Usuario no encontrado
{% endapi-method-response-example-description %}

```
{
"message": texto explicativo
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api" path="/v1/users/" %}
{% api-method-summary %}
Create user
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
JWT del usuario administrador registrado
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="isAdmin" type="boolean" required=true %}
Indicador de si es un usuario administrador o no
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
contraseña del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email valido para la creacion del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Se crea usuario
{% endapi-method-response-example-description %}

```
{
"email" : correo del usuario creado,
"isAdmin" : indicador del usuario creado
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
"error message" : mensaje explicativo de error en validacion
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Vacunatorio

{% api-method method="post" host="https://api" path="/v1/vaccunatory/" %}
{% api-method-summary %}
Crear vacunatorio
{% endapi-method-summary %}

{% api-method-description %}
Crea el vacunatorio 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
JWT que identifica al usuario
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="Name" type="string" required=true %}
Nombre del vacunatorio
{% endapi-method-parameter %}

{% api-method-parameter name="Schedule " type="integer" required=true %}
Horario de vacunacion \(1- todo el dia, 2- matutino, 3 - vespertino\)
{% endapi-method-parameter %}

{% api-method-parameter name="Zone" type="integer" required=true %}
Zona del departamento o codigo de dos digitos entre 1 y 50 inclusive
{% endapi-method-parameter %}

{% api-method-parameter name="State" type="integer" required=true %}
Departamento asignado segun codigo de codificacion
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
"id" : identificador unico del vacunatorio a nivel pais
"name": nombre del vacunatorio
"schedule" : horario del vacunatorio
"state" : departamento del vacunatorio
"zone" : zona dentro del departamento
"quota" : cupo del vacunatorio, por defecto 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
"message" : mensaje explicativo de error
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="api" path="/v1/vaccunatory/quota" %}
{% api-method-summary %}
Actualizar cupos de vacunatorio
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
JWT del usuario
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="AgeGroup" type="object" required=false %}
Array que marca franja etaria.
{% endapi-method-parameter %}

{% api-method-parameter name="PriorityGroup" type="integer" required=false %}
Grupo prioritario del 1 al 4.
{% endapi-method-parameter %}

{% api-method-parameter name="Quota" type="integer" required=true %}
Cupos que se disponibilizan
{% endapi-method-parameter %}

{% api-method-parameter name="ToDate" type="object" required=true %}
Fecha en la que se terminan los cupos disponibles
{% endapi-method-parameter %}

{% api-method-parameter name="FromDate" type="object" required=true %}
Fecha desde la que hay cupos disponibles
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
Codigo unico del vacunatorio
{% endapi-method-parameter %}

{% api-method-parameter name="Zone" type="integer" required=true %}
Zona del vacunatorio dentro del departamento
{% endapi-method-parameter %}

{% api-method-parameter name="State" type="integer" required=true %}
Codigo del departamento del vacunatorio
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
"message": mensaje de exito
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
En caso de no cumplirse una validacion o de no poner ni AgeGroup ni PriorityGroup \(o de marcar ambos en simultaneo\) se produce un error.
{% endapi-method-response-example-description %}

```
"message": error message
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Vaccunacion

{% api-method method="post" host="api" path="/v1/vaccination/" %}
{% api-method-summary %}
Registrar vacunacion
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
JWT que identifica a usuario vacunador
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="Date" type="object" required=true %}
Fecha de vacunacion
{% endapi-method-parameter %}

{% api-method-parameter name="DocumentId" type="string" required=true %}
Cedula de identidad del vacunado, sin puntos ni guion con codigo verificador
{% endapi-method-parameter %}

{% api-method-parameter name="VacunatoryId" type="string" required=true %}
Codigo unico del vacunatorio
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
Date,
DocumentId,
VaccunatoryId
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
En caso de tener un error de validacion se retorna un mensaje explicativo
{% endapi-method-response-example-description %}

```
{message: mensaje explicativo}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="api" path="/v1/vaccination/:Vaccunatoryid" %}
{% api-method-summary %}
Consulta sobre plan de vacunacion
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="VaccunatoryId" type="string" required=true %}
Id del vacunatorio a consultar
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
JWT del usuario
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="ToDate" type="object" required=true %}
Fecha final a consultar
{% endapi-method-parameter %}

{% api-method-parameter name="FromDate" type="object" required=true %}
Fecha inicial a consultar
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
VaccunatoryInfo: ["id","state","zone","name"]
VaccinatedQuantity: "cantidad de vacunas"
RemainingVaccines: "cantidad de vacunas restantes"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
"message": error de fecha o de algun campo
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
De no encontrar el vacunatorio se retorna esto
{% endapi-method-response-example-description %}

```
"message": mensaje explicativo
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="api" path="/v1/vaccination/" %}
{% api-method-summary %}
Consulta 2
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=false %}
JWT del usuario
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Lista por departamento y zona la cantidad de reservas pendientes por asignar
{% endapi-method-response-example-description %}

```
{
 RemainingList: ["state", "zone", "remainingCount"]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
