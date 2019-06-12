---
title: 'Lync Server 2013: Rutas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Rutas de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes que hacen los usuarios de telefonía IP. Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E. 164, si es necesario, e intenta hacerlo coincidir con el URI del SIP. Si el servidor no puede establecer esa coincidencia, aplicará la lógica de enrutamiento de llamadas salientes basándose en el número. El paso final para definir la lógica consiste en crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino indicados en cada plan de marcado.

Antes de definir las rutas de llamadas salientes, necesitas completar los pasos siguientes:

  - Implementa uno o más troncos.

  - Crea planes de marcado, según sea necesario, para sitios, usuarios individuales y objetos de contacto.

  - Crea registros de uso de la red telefónica conmutada (RTC).

Además, para habilitar el enrutamiento de llamadas salientes, necesitas crear y asignar una o más directivas de voz. Puedes hacerlo antes o después de definir las rutas de llamadas salientes.

Para cada ruta, necesitas especificar:

  - Un nombre con el que se pueda identificar fácilmente la ruta.

  - Una descripción opcional en los casos en que el nombre no sea suficiente para describir la ruta.

  - El patrón coincidente de la expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con excepciones a las que no se necesita aplicar el patrón coincidente.

  - Uno o más troncos que deseas asignar a la ruta.

  - Los registros de uso de RTC que los usuarios necesitan tener para llamar a los números que coincidan con la expresión regular del número de teléfono de destino.

Puede especificar rutas de llamadas en el panel de control de Lync Server. Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor, que Lync Server usa para enrutar las llamadas dirigidas a la RTC.

<div>

## <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Lync Server proporciona flexibilidad a la hora de enrutar las llamadas a la RTC. Una ruta de voz especifica a la RTC un conjunto de troncos que pueden usarse para una llamada de voz concreta. Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha. Esta asociación lógica permite asociar un servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace. Al definir una ruta de llamada, especifica los troncos asociados a esa ruta, pero no especifica qué servidores de mediación están asociados a la ruta. Para crear troncos definiendo las relaciones entre los servidores de mediación y las puertas de enlace RTC, IP-PBX y los controladores de borde de sesión (SBCs), use el generador de topología.

</div>

<div>

## <a name="least-cost-routing"></a>Enrutamiento de menor coste

La capacidad para especificar los troncos a los que se redirigen varios números te permite determinar e implementar las rutas de menor coste. La regla general para seleccionar troncos es elegir el que tenga la puerta de enlace más cercana a la ubicación del número de destino a fin de minimizar los gastos de larga distancia. Por ejemplo, si te encontraras en Nueva York y llamaras a Roma, llevarías la llamada a través de la red IP hasta el tronco con la puerta de enlace más cercana a la oficina de Roma, por lo que solo necesitarías pagar el precio de una llamada local.

Para obtener un ejemplo de cómo se puede usar el enrutamiento de menor costo, considere lo siguiente: fabrikam decide permitir que los usuarios de alemán llamen a números de Estados Unidos con el tronco de Estados Unidos. Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios del servidor de Lync de Estados Unidos a Alemania y países o regiones adyacentes terminen en el tronco con el Gateway en Alemania. Este enrutamiento ahorrará dinero, porque una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Convertir cadenas de marcado salientes

Lync Server 2013, al igual que sus predecesores inmediatos, requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL). Para los troncos con puertas de enlace o las sucursales privadas (PBX) que requieren números traducidos a formatos de marcado locales, Lync Server 2013 le permite crear una o más reglas que ayuden a manipular el número llamado (es decir, URI de solicitud) antes de enrutarlo al tronco. Por ejemplo, podrías escribir una regla para quitar +44 del encabezado de la cadena de marcado y cambiarlo por 0144.

Con Lync Server 2013, es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.

En el planeamiento de los troncos que asocian puertas de enlace: pares de puertos con el servidor de mediación: pares de puertos, puede ser útil agrupar los troncos con requisitos de marcado local similares y, por lo tanto, reducir el número de reglas de traducción necesarias y el tiempo que se tarda en escribirlas.

</div>

<div>

## <a name="configuring-caller-id"></a>Configurar el identificador de llamada

Lync Server proporciona una forma de manipular la identificación de llamadas para las llamadas salientes. Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y reemplazarlas con el número de departamento o corporativo genérico, un administrador puede hacerlo con el panel de control de Lync Server para suprimir la identificación de llamadas y reemplazarla por una IDENTIFICADOR de llamada alternativo especificado. Al planificar la lógica de enrutamiento, ten en cuenta si querrás esta opción para usuarios individuales, grupos o sitios o, incluso, para todos los empleados.

<div>


> [!NOTE]  
> En el caso de las llamadas que se desvían a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original. Esto puede hacer que la llamada omita la configuración de privacidad o de No molestar que pueda haber establecido el destinatario de la llamada.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Lógica de enrutamiento adicional

Al crear rutas de llamadas salientes, necesitas tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:

  - Si se establece una llamada a través de un límite federado, la parte correspondiente al dominio en el URI se usa para redirigir la llamada a la empresa responsable de aplicar la lógica de enrutamiento saliente.

  - Si la parte correspondiente al dominio en el URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento saliente en el servidor no procesará la llamada.

  - Si un usuario no está habilitado para Enterprise Voice, el servidor aplicará otra lógica de enrutamiento, según corresponda.

  - Si se redirige una llamada a una puerta de enlace totalmente ocupada (todas las principales líneas de conexión están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento saliente redirige la llamada a la siguiente ruta de menor coste. Esto necesita analizarse minuciosamente, ya que una puerta de enlace con un tamaño adecuado para una oficina pequeña internacional (por ejemplo, de Zúrich), podría transportar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza. Si el tamaño de la puerta de enlace no se diseñara correctamente para este tráfico adicional, las llamadas a Suiza podrían redirigirse a través de una puerta de enlace de Alemania, lo que daría lugar a tarifas más altas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

