# Arquitectura

{% api-method method="post" host="https://api" path="/v1/booking/" %}
{% api-method-summary %}
Booking
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



