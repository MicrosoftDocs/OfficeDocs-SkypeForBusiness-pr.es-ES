---
title: 'Lync Server 2013: definir los elementos de red que se usan para determinar la ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Si está configurando su infraestructura de Lync Server para admitir la detección automática de la ubicación del cliente, primero debe decidir qué elementos de la red va a usar para asignar las personas que llaman a ubicaciones. En Lync Server 2013, puede asociar los siguientes elementos de red de la capa 2 y la capa 3 con ubicaciones:

  - Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)

  - Puerto del conmutador LLDP (nivel 2)

  - Identificadores del chasis del conmutador LLDP (nivel 2)

  - Subredes IP (nivel 3)

  - Direcciones MAC de cliente (nivel 2)

Los elementos de red se enumeran en orden de prioridad. Si un cliente puede encontrarse usando más de un elemento de red, Lync Server usa el orden de prioridad para determinar qué mecanismo usar.

En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.

<div>


> [!IMPORTANT]  
> Al usar elementos de red para asignar las personas que llaman a ubicaciones, es muy importante que mantenga actualizada la base de datos del servicio de información de ubicación. Por ejemplo, si agregas o cambias un elemento de red, como cuando agregas un WAP, necesitarás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones.



</div>

<div>

## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación al usar la dirección BSSID del WAP. Si el cliente está utilizando un perfil móvil, puede que el WAP indicado sea el más cercano y es posible, incluso, conectarse a un WAP que se encuentre en otra planta del edificio. Para indicar que la ubicación es aproximada, puedes anteponer Near o Close to al valor de ubicación del descriptor.

Este método de ubicación supone que el BSSID de cada WAP es estático. Sin embargo, si su proveedor WAP usa BSSIDs asignados dinámicamente, los BSSID que se obtengan de un WAP podrían cambiar (esto puede ocurrir después de un cambio de configuración WAP), y los clientes inalámbricos podrían permanecer en una situación en la que no reciban una ubicación. Para evitar esta posibilidad, debe rellenar la base de datos de servicios de información de ubicación con ERLs para todas las direcciones BSSID posibles que cada WAP usa.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten el Protocolo de detección de nivel de vínculo: detección de extremos de medios (LLDP-MED) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puedes asociar las ERL únicamente en el identificador de chasis del conmutador, o bien los puedes asignar en el puerto.

<div>


> [!NOTE]  
> Lync Server 2013 admite el uso de LLDP-MED para determinar las ubicaciones de los dispositivos Lync Phone Edition y de Lync 2013 en Windows 8. Si necesita usar datos de capa 2 a nivel de conmutador para determinar la ubicación de otros clientes de Lync basados en PC con cable, debe usar el método de dirección MAC del cliente.



</div>

</div>

<div>

## <a name="subnet"></a>Subred

Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Lync Server que se pueden usar para detectar automáticamente la ubicación de los clientes. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes cableados. Pero, antes de decidir usar subredes, necesitarás hacerte las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:

  - ¿Existe una o más subredes de clientes que cubran varios pisos?

  - ¿Existe una o más subredes que cubran más de un edificio?

  - ¿Cuánto espacio del piso queda cubierto por cada subred de cliente?

Si la subred cubre un área demasiado extensa, es posible que debas usar otro mecanismo para ubicar a clientes. Pero, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el coste y la complejidad de soluciones basadas en SNMP de terceros.

</div>

<div>

## <a name="client-mac-address"></a>Dirección MAC de cliente

Para usar la dirección MAC de un equipo cliente para ubicar a una persona que llama, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda descubrir las direcciones MAC de los clientes de Lync conectados a ellos (o a través de ellos). La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes. Durante la solicitud de un cliente de Lync al servicio de información de ubicación, el servicio de información de ubicación consulta la aplicación de terceros usando la dirección MAC del cliente y, a continuación, devuelve las direcciones IP del modificador y los identificadores de Puerto coincidentes. El servicio de información de ubicación usa esta información para consultar sus Wiremap de capa 2 publicadas y devuelve la ubicación al cliente. Si utilizas esta opción, asegúrate de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.

<div>


> [!NOTE]  
> Algunas soluciones SNMP de terceros pueden admitir modificadores de acceso no administrados; Si el modificador que ofrece servicio al cliente de Lync no está administrado pero tiene un vínculo superior a un conmutador de distribución administrada, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite que el servicio de información de ubicación identifique la ubicación del usuario. Pero, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el chasis del conmutador de acceso, pero no en el puerto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

