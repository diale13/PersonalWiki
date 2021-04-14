# 10 - Insufficient logging and monitoring

{% embed url="https://owasp.org/www-project-top-ten/2017/A10\_2017-Insufficient\_Logging%2526Monitoring" %}

**¿Que es?** No haber visto el ataque mientras sucedia o siquiera saber que ocurrio

**¿Impacto?** Un atacante puede persistir en el sistema, extraer o manipular datos sin conocimiento del dueño. 

**¿Como prevenir?**

* Mantener logs de los eventos importantes y validaciones
* Asegurar que un log pueda ser facilmente consumido pero no verificado
* Mejorar continuamente el monitoreo y alertas
* **Rotate**: cambiar credenciales , **Repave**: volver a ultimo estado de config valido \(golden image\), **Repair**: cuando hay patch lo aplicamos.

![](../../../.gitbook/assets/imagen%20%28439%29.png)

![](../../../.gitbook/assets/imagen%20%28443%29.png)

