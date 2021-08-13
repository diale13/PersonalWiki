# Asesoria

## Comprando productos de seguridad

• Idealmente, comprar productos de seguridad debería incluir: 

• \(1\) – evaluar las necesidades para determinar los requisitos. 

• \(2\) – identificar el producto que cumplirá esos requisitos.

 • \(3\) – comprar el producto y desplegarlo.



 • El problema: la mayoría de los clientes no tienen la experiencia para realizar estos pasos de manera efectiva. 

• Una solución: proporcionar un proceso estandarizado de evaluación independiente provisto por un equipo de expertos para proporcionar un nivel certificado de confianza para productos de seguridad.

## Metodología de evaluación

• Un estándar de evaluación proporciona lo siguiente: • Un conjunto de requisitos que definen la funcionalidad de seguridad. • Un conjunto de requisitos de aseguramiento necesarios para establecer los requerimientos funcionales. • Una metodología para determinar que los requerimientos funcionales se cumplen. • Una medida del resultado de la evaluación que indica la confiabilidad del sistema evaluado.

## Funciones Criptográficas

• Para las funciones criptográficas, se requiere que las agencias federales usen productos que hayan sido aprobados por la NSA, o hayan sido validados a FIPS 140-1 o 140-2, requisito de seguridad para módulos criptográficos. • Aproximadamente 150 proveedores de módulos criptográficos tenían laboratorios independientes para realizar pruebas de cumplimiento / conformidad de sus módulos. • FIPS 140-2 define cuatro niveles para la certificación de dispositivos criptografía diseñados para la protección de información sensibles pero no clasificada.

## Niveles FIPS 140-2

Para productos criptográficos, el gobierno brinda orientación en forma de estándares FIPS 140-1 y 140-2.

Las normas de certificación para productos de seguridad ayudarían a que el consumidor entienda lo que necesita y lo que esta comprando.

• Estos son los niveles de certificación para los dispositivos criptográficos: • Nivel 1: seguridad básica; al menos una función o algoritmo aprobado • Nivel 2: seguridad física mejorada, embalaje inviolable • Nivel 3: fuerte resistencia a la manipulación y contramedidas • Nivel 4: competa protección envolvente, incluida la inmediata puesta a cero de claves en caso de manipulación

## Common Criteria

• La necesidad de criterios de evaluación de sistemas seguros condujo a numerosos países a desarrollar los suyos. Eso ha sido en gran parte reemplazado por los “Common Criteria”, adoptados por unos 26 países, incluidos los EE.UU.

Comprende: • Los documentos CC. • La metodología de evaluación CC \(CEM\). • Metodologías de evaluación específicas de un país determinado llamadas Esquemas de Evaluación o Esquemas Nacionales. • Evaluación \(hasta cierto nivel\) por parte de un país firmante son respetadas por todos los demás.

Cualquier discusión sobre los “Common Criteria” tiene a ser muy pesado en base a acrónimos. Aquí hay algunos: • TOE \(Target of Evaluation\) el sistema presentado para evaluación. • ST \(Security Target\) conjunto de requisitos de seguridad para ser utilizado como base de la evaluación. • EAL \(Evaluation Assurance Level\) el nivel de certificación buscado. • TSF \(TOE Security Funcionts\) el conjunto de todos los hardware, software y firmware necesarios para la aplicación de la política.

Hay dos tipos de evaluaciones bajo el Common Criteria \(CC\) • \(1\) – evaluaciones de perfiles de protección \(PP\), un conjunto de requisitos de seguridad independientes de la implementación para una categoría de productos o sistemas. • \(2\) – evaluaciones de productos o sistemas contra un objetivo de seguridad \(ST\).

• Un PP es una descripción de una familia de productos en términos de amenazas, cuestiones y suposiciones ambientales, objetivos de seguridad y requisitos de los “Common Criteria”. • Incluye: • \(1\) – introducción, que contiene una identificación e información general del sistema • \(2\) – Descripción de la familia del producto o del sistema • \(3\) – Entorno de seguridad familiar del producto o del sistema • \(4\) – Objetivos de seguridad • \(5\) – Requisitos de seguridad de TI • \(6\) – Justificación • Algunos ejemplos: antivirus en estacione de trabajo, biometría, firewalls, detección de intrusos, sistemas operativos, PKI, base de datos confiables. • Aproximadamente 50 perfiles de protección existen actualmente con más en desarrollo

El objetivo de seguridad es un documento que contiene los requisitos de seguridad de un producto a evaluar \(TOE\), y especifica las medidas ofrecidas por el producto para cumplir con esos requisitos. Eso puede coincidir con un perfil de protección. • \(1\) – Introducción • \(2\) – Descripción TOE • \(3\) – Entorno de seguridad TOE: suposiciones, amenazas, políticas de seguridad organizacionales • \(4\) – Objetivos de seguridad • \(5\) – Requisitos de seguridad de TI • \(6\) – Especificación de resumen TOE • \(7\) – Reclamaciones de perfil de protección • \(8\) – Justificación: evidente que el ST es un conjunto completo de requisitos y que el TOE proporciona medidas para abordar los requisitos

## Ejemplo PP: WBIS

• Sistema alemán de identificación de contenedores de residuos \(German Waste Bin Identification System – WBIS\) evaluado para EAL1. • Los contenedores de basura tienen etiquetas de identificación, leídas por radio de corto alcance en camiones que los pesan cuando se recoge la basura, almacena la información y más tarde lo transmite a las oficinas gubernamentales para la facturación. • Las etiquetas de identificación contienen número que son únicos pero no son confidenciales.

 **Bienes** • Registra que se limpió un contenedor de basura \(basura recolectada\) que consiste en \(identificador de bin, sello de tiempo, peso\).

**Supuestos ambientales** • A.ID: la etiqueta se adjunta a la papelera • A.Tursted: el equipo está autorizado y es confiable • A.Access: el acceso al sistema está protegido • A.Check: el operador verifica a intervalos que la transferencia de datos es completa. • A.Backup de seguridad: el operador realiza copias de seguridad de los datos en intervalos.

**Amenazas** • T.Man: el atacante rompe la etiqueta • T.Jam1: el atacante envía una señal para corromper los datos leídos por el camión • T.Jam2: el atacante corrompe los datos durante el procesamiento y el almacenamiento dentro del camión • T.Create: el atacante crea y difunde datos arbitrarios

 **Políticas de seguridad organizacional** • P.Safe: copia de seguridad secundaria tolerante a errores de datos dentro del camión

**Objetivos de seguridad** • OT.Inv1: detectar etiquetas de identificación no válidas • OT.Inv2: detectar mensajes borrados de bin no válidos • OT.Safe: tolerancia a fallas • Requerimientos de seguridad • Autenticación de datos \(FDP DAU.1\) • Protección de integridad de transferencia interna \(FDP ITT.1\) • Integridad de datos almacenados \(FDP SDI.1\)

![](../.gitbook/assets/imagen%20%283%29.png)

## Niveles de aseguramiento

 • La evaluación bajo los “Common Criteria” se dirigen a un nivel específico de rigor. 

• El vendedor proporciona el aseguramiento de que el rigor correspondiente se aplicó durante el desarrollo y la prueba- 

• EAL1: probado funcionalmente 

• EAL2: probado estructuralmente 

• EAL3: probado metodológicamente y verificado 

• EAL4: diseñado metodológicamente, probado y revisado 

• EAL5: diseñado y probado semi-formalmente 

• EAL6: diseño verificado y probado semi-formalmente 

• EAL7: diseño verificado y probado formalmente

![](../.gitbook/assets/imagen%20%2812%29.png)

## El Certificado CC

•Emitir una certificación CC significa que el gobierno de el país donde se realiza la evaluación cree que la evaluación fue conducida apropiadamente. 

•Indica un esfuerzo de buena fe para garantizar que el producto cumple con los reclamos del vendedor. No asegura la exactitud absoluta o la idoneidad para requisitos particulares. 

•No excluye el marketing excesivo del vendedor 

• Versiones posteriores pueden requerir una nueva prueba.



## Laboratorios de testeo

 • Los proveedores de productos no pueden auto-certificarse; las pruebas de evaluación deben ser realizadas por una organización independiente acreditada para realizar pruebas CC. El NIST \(National Institute of Standards and Technologies\) es responsable de administrar este proceso en los EE.UU. • Las evaluaciones se realizan \(por una tarifa\) por laboratorios comerciales que están certificados por NIST. • Pruebas de laboratorios independientes hasta EAL4. Actualmente 10 laboratorios en los EE.UU., con uno \(atsec\) en Austin. 

• Los costos de prueba son impulsados por un mercado relativamente pequeño, la complejidad y la necesidad de un personal capacitado.

 • EAL2 cuesta $ 100K a $ 70K y tarda de 4 a 6 meses 

• EAL4 cuesta $ 300K a $ 750K y demora de uno a dos años

• Un producto para ser probado en EAL5 / EAL6 / EAL7 debe haber sido diseñado utilizando métodos formales \(matemáticos\). 

• No se puede aplicar ingeniería inversa al modelo desde el código. • Los componentes deben mantenerse pequeños e independientes. 

• Se requiere una amplia documentación.

 • En los EE.UU, solo la NSA realiza pruebas para EAL5 y superiores. 

• Una agencia de EE.UU., no aceptaría una certificación para EAL5 o superior emitida por otro país.



## Resumen 

• Los Niveles de Aseguramiento de Evaluación \(1 – 7\) definen el cuidado con el cual el producto fue desarrollado y el rigor del proceso de evaluación. 

• La certificación de un país significa que la evaluación fue llevada a cabo con cuidado y de buena fe, no es que el producto sea adecuado o seguro. 

• Las evaluaciones son realizadas por laboratorios independientes por una tarifa. Los laboratorios están autorizados por la autoridad nacional de pruebas.





