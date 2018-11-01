---
title: 'Lync Server 2013: Rutas de voz'
TOCTitle: Rutas de voz
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48276253
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rutas de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

Las rutas de llamadas especifican la forma en que Lync Server administra las llamadas salientes realizadas por usuarios de Telefonía IP empresarial. Cuando un usuario marca un número, el Servidor front-end normaliza la cadena de marcado al formato E.164, si es necesario, e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede establecer esa coincidencia, aplicará la lógica de enrutamiento de llamadas salientes basándose en el número. El paso final para definir la lógica consiste en crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino indicados en cada plan de marcado.

Antes de definir las rutas de llamadas salientes, debe completar los pasos siguientes:

  - Implementar uno o más troncos.

  - Crear planes de marcado, según sea preciso, para sitios, usuarios individuales y objetos de contacto.

  - Crear registros de uso de la red telefónica conmutada (RTC).

Además, para habilitar el enrutamiento de llamadas salientes, debe crear y asignar una o más directivas de voz. Puede hacerlo antes o después de definir las rutas de llamada salientes.

Para cada ruta, debe especificar:

  - Un nombre con el que se pueda identificar fácilmente la ruta.

  - Una descripción opcional en los casos en que el nombre no sea suficiente para describir la ruta.

  - El patrón coincidente de la expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con excepciones a las que no se debe aplicar el patrón coincidente.

  - Uno o más troncos que desea asignar a la ruta.

  - Los registros de uso de RTC que los usuarios deben tener para llamar a los números que coincidan con la expresión regular de número de teléfono de destino.

Puede especificar rutas de llamadas en el Panel de control de Lync Server. Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor que Lync Server usa para enrutar llamadas cuyo destino es la RTC.

## Compatibilidad con troncos M:N

Lync Server permite enrutar las llamadas a la RTC de manera flexible. Una ruta de voz especifica a la RTC un conjunto de troncos que pueden usarse para una llamada de voz concreta. Un tronco asocia un Servidor de mediación y un número de puerto con un número de puerto de escucha y una puerta de enlace RTC. Esta asociación lógica permite asociar un Servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace. Al definir una ruta de llamada, se especifican los troncos asociados con dicha ruta, pero no qué Servidores de mediación se asocian con la ruta. Para crear troncos definiendo las relaciones entre Servidores de mediación y las puertas de enlace RTC, IP-PBX y controladores de borde de sesión (SBC), use la Generador de topologías.

## Enrutamiento de menor costo

La capacidad para especificar los troncos a los que se enrutan varios números permite determinar e implementar las rutas de menor costo. La regla general para seleccionar troncos es elegir el que tenga la puerta de enlace más cercana a la ubicación del número de destino a fin de minimizar los gastos de larga distancia. Por ejemplo, si se encontrara en Nueva York y llamara a Roma, llevaría la llamada a través de la red IP hasta el tronco con la puerta de enlace más cercana a la oficina de Roma, por lo que solo debería pagar el precio de una llamada local.

Si desea un ejemplo sobre cómo se puede usar el enrutamiento de menor costo, considere el siguiente ejemplo: Fabrikam decide permitir a los usuarios alemanes marcar números de Estados Unidos mediante el tronco. Fabrikam también desea configurar el sistema de modo que todas las llamadas de usuarios de Lync Server de Estados Unidos a Alemania, y países o regiones vecinos, terminen en el tronco con la puerta de enlace alemana. Este enrutamiento permite ahorrar dinero puesto que una llamada de Alemania a Austria, por ejemplo, es más barata que una llamada de Estados Unidos a Austria.

## Conversión de cadenas de marcado salientes

Lync Server 2013, como sus versiones anteriores, requiere que todas las cadenas de marcado se normalicen al formato E.164 para realizar búsquedas inversas de números (RNL). En el caso de troncos con puertas de enlace o centrales de conmutación privadas (PBX) que requieran convertir números a los formatos de marcado locales, Lync Server 2013 permite crear una o más reglas que ayuden a manipular el número llamado (es decir, el URI solicitado) antes de enrutarlo al tronco. Por ejemplo, podría escribir una regla para quitar +44 del encabezado de la cadena de marcado y sustituirlo por 0144 .

Con Lync Server 2013, es posible crear una o más reglas que ayuden a manipular el número que realiza la llamada antes de enrutarla al tronco.

A la hora de planear los troncos que asociarán parejas de puertos/puertas de enlace con parejas de Servidor de mediación/puertos, puede resultar útil agrupar los troncos que tengan requisitos de marcado local similares para reducir la cantidad de reglas de conversión necesarias y el tiempo que lleva escribirlas.

## Configuración del identificador de llamada

Lync Server permite manipular el identificador de llamada para las llamadas salientes. Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y sustituirlas por el número de departamento o por el número de corporación genérico, un administrador puede hacerlo mediante el Panel de control de Lync Server para suprimir el identificador de llamada y sustituirlo por un identificador de llamada alternativo especificado. Al planear la lógica de enrutamiento, tenga en cuenta si querrá esta opción para usuarios individuales, grupos o sitios o, incluso, para todos los empleados.


> [!NOTE]
> En el caso de las llamadas que se vuelven a enrutar a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original. Esto puede hacer que la llamada omita la configuración de privacidad o de No molestar que pueda haber establecido el autor de la llamada.



## Lógica de enrutamiento adicional

Al crear rutas de llamadas salientes, debe tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:

  - Si se establece una llamada a través de un límite federado, la parte correspondiente al dominio en el URI se usa para enrutar la llamada a la empresa responsable de aplicar la lógica de enrutamiento saliente.

  - Si la parte correspondiente al dominio en el URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento saliente en el servidor no procesará la llamada.

  - Si un usuario no está habilitado para Telefonía IP empresarial, el servidor aplicará otra lógica de enrutamiento según corresponda.

  - Si se enruta una llamada a una puerta de enlace totalmente ocupada (todas las principales líneas de conexión están ocupadas), la puerta de enlace rechazará la llamada y la lógica de enrutamiento saliente redirige la llamada a la siguiente ruta de menor costo. Esto debe analizarse minuciosamente ya que una puerta de enlace con un tamaño adecuado para una oficina pequeña de Europa (por ejemplo, de Zúrich), podría transportar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza. Si el tamaño de la puerta de enlace no se diseñara correctamente para este tráfico adicional, las llamadas a Suiza podrían enrutarse a través de una puerta de enlace de Alemania, lo que daría lugar a tarifas más altas.

