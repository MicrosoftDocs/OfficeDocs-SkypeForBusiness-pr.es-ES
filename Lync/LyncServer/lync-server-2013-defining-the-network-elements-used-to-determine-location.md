---
title: 'Lync Server 2013: definir los elementos de red que se usan para determinar la ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cfedb09cdcdebdc12cdd2aed69e56532dcca5ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504507"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Si está configurando su infraestructura de Lync Server para admitir la detección automática de ubicaciones de clientes, primero debe decidir qué elementos de red va a usar para asignar los autores de las llamadas a las ubicaciones. En Lync Server 2013, puede asociar los siguientes elementos de red de nivel 2 y 3 con ubicaciones:

  - Direcciones de identificación de conjunto de servicio (BSSID) básicas de punto de acceso inalámbrico (WAP) (nivel 2)

  - Puerto del conmutador LLDP (nivel 2)

  - Identificadores del chasis del conmutador LLDP (nivel 2)

  - Subredes IP (nivel 3)

  - Direcciones MAC de cliente (nivel 2)

Los elementos de la red se muestran en orden de prioridad. Si un cliente se puede ubicar mediante más de un elemento de red, Lync Server usa el orden de prioridad para determinar el mecanismo que se va a usar.

En las secciones siguientes se proporcionan más detalles sobre el uso de cada elemento de red.

<div>


> [!IMPORTANT]  
> Cuando se usan elementos de red para asignar los autores de las llamadas a las ubicaciones, es fundamental tener la actualización de la base de datos del servicio de información de ubicación. Por ejemplo, si agregas o cambias un elemento de red, como agregar un WAP, deberás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones.



</div>

<div>

## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación usa la dirección BSSID del WAP para determinar su ubicación. Si el cliente está en itinerancia, el WAP indicado puede que no sea el más próximo, y es incluso posible retomar un WAP que se encuentra en un piso diferente del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor near o Close.

Este método de ubicación presupone que el BSSID de cada WAP es estático. Sin embargo, si su proveedor WAP usa BSSIDs asignada dinámicamente, los BSSID que se obtienen de un WAP podrían cambiar (esto puede ocurrir después de un cambio de configuración WAP) y los clientes inalámbricos pueden quedar en una situación en la que no reciben una ubicación. Para evitar esta posibilidad, debe rellenar la base de datos del servicio de información de ubicaciones con Erl para todas las direcciones BSSID posibles usadas por cada WAP.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten la detección de la capa de vínculo Protocol-Media detección de extremos (LLDP-MED) pueden anunciar información de identidades y puertos a clientes compatibles con LLDP-MED, que se pueden consultar en la base de datos de ubicaciones para proporcionar la ubicación del dispositivo. Puede asociar ERL únicamente en el identificador del chasis del conmutador, o puede asignarlos al nivel de puerto.

<div>


> [!NOTE]  
> Lync Server 2013 admite el uso de LLDP-MED para determinar las ubicaciones de los dispositivos Lync Phone Edition y Lync 2013 en Windows 8. Si necesita usar datos de capa 2 a nivel de conmutador para determinar la ubicación de otros clientes de Lync basados en PC cableados, debe usar el método de dirección MAC del cliente.



</div>

</div>

<div>

## <a name="subnet"></a>Subred

Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Lync Server que se pueden usar para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más fácil para configurar y administrar clientes con cable. Sin embargo, antes de decidirse a usar subredes, puede usar las siguientes preguntas para determinar si la especificidad de la ubicación de la subred es lo suficientemente adecuada como para buscar un cliente de forma precisa:

  - ¿Hay una o más subredes de clientes que cubran varios pisos?

  - ¿Hay una o más subredes que cubran más de un edificio?

  - ¿Cuánto espacio de planta cubre cada subred de cliente?

Si la subred cubre un área demasiado amplia, es posible que deba usar otro mecanismo para localizar clientes. Sin embargo, si es posible, recomendamos que los clientes reorganicen sus subredes IP para cumplir con los requisitos de especificidad de la ubicación ERL, en lugar de incurrir en el coste y la complejidad de las soluciones basadas en SNMP de terceros.

</div>

<div>

## <a name="client-mac-address"></a>Dirección MAC del cliente

Para usar la dirección MAC de un equipo cliente para localizar a una persona que llama, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda detectar las direcciones MAC de los clientes de Lync conectados a los clientes (o a través de los mismos). La solución SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de extremo conectadas a cada puerto y obtiene los identificadores de Puerto correspondientes. Durante la solicitud de un cliente de Lync al servicio de información de ubicación, el servicio de información de ubicación consulta a la aplicación de terceros usando la dirección MAC del cliente y, a continuación, devuelve las direcciones IP del conmutador y los identificadores de Puerto correspondientes. El servicio de información de ubicación usa esta información para consultar sus cableado de capa 2 publicadas para un registro que coincida y devuelve la ubicación al cliente. Si usa esta opción, asegúrese de que los identificadores de puerto del conmutador sean coherentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicada.

<div>


> [!NOTE]  
> Algunas soluciones SNMP de terceros pueden admitir conmutadores de acceso no administrados; Si el conmutador que dirige el cliente de Lync no está administrado pero tiene un vínculo superior a un conmutador de distribución administrada, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite que el servicio de información de ubicación identifique la ubicación del usuario. Sin embargo, es posible asignar un solo ERL a todos los puertos del conmutador no administrado, por lo que la especificidad de la ubicación solo está disponible en el nivel de chasis del conmutador de acceso, no en el nivel de puerto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

