---
title: "Lync Server 2013: Definir elementos de red que se usan para determinar la ubicación"
TOCTitle: Definir los elementos de red que se usan para determinar la ubicación
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48275682
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Si desea configurar su infraestructura de Lync Server para que admita la detección automática de la ubicación del cliente, deberá decidir en primer lugar qué elementos de red va a usar para asignar las personas que llamen a las ubicaciones. En Lync Server 2013, puede asociar los siguientes elementos de red de nivel 2 y nivel 3 con las ubicaciones:

  - Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)

  - Puerto del interruptor LLDP (nivel 2)

  - Identificadores del chasis del conmutador LLDP (nivel 2)

  - Subredes IP (nivel 3)

  - Direcciones MAC de cliente (nivel 2)

Los elementos de red se enumeran en orden de prioridad. Si un cliente puede localizarse usando más de un elemento de red, Lync Server usará el orden de prioridad para determinar qué mecanismo usar.

En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.

> [!IMPORTANT]  
> Cuando usa elementos de la red para asignar las personas que llaman a las ubicaciones, es muy importante que mantenga la base de datos del Servicio de información de ubicaciones actualizada. Por ejemplo, si agrega o cambia un elemento de red, como cuando agrega un WAP, deberá eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones.



## Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación usando la dirección BSSID del WAP. Si el cliente está utilizando un perfil móvil, puede que el WAP indicado sea el más cercano y es posible incluso conectarse a un WAP que se encuentre en otra planta del edificio. Para indicar que la ubicación es aproximada, anteponga al valor de ubicación el descriptor Near o Close to.

Este método de ubicación asume que el BSSID de cada WAP es estático. Sin embargo, si su proveedor de WAP usa BSSID asignados dinámicamente, el BSSID que se obtiene de un WAP podría cambiar (puede ocurrir, por ejemplo, tras un cambio de configuración WAP), con lo que los clientes inalámbricos podrían dejar de recibir una ubicación. Para evitar que esto suceda, rellene la base de datos del Servicio de información de ubicaciones con las ERL de todas las direcciones de BSSID posibles que pueda usar cada WAP.

## Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puede asociar las ERL únicamente en el identificador de chasis del conmutador o bien los puede asignar al nivel del puerto.


> [!NOTE]
> Lync Server 2013 admite el uso de LLDP-MED para determinar las ubicaciones solo de dispositivos Lync Phone Edition y de dispositivos de Lync 2013 que se ejecuten en Windows 8. Si necesita utilizar datos de nivel 2 de nivel de conmutador para determinar la ubicación de otros clientes de Lync basados en PC, deberá usar el método basado en las direcciones MAC de cliente.



## Subred

Las subredes IP de nivel 3 constituyen un mecanismo compatible con todos los clientes de Lync Server que se usa para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes conectados por cable. No obstante, antes de decidir si usar subredes, deberá hacerse las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:

  - ¿Existe una o más subredes de clientes que cubran varios pisos?

  - ¿Existe una o más subredes que cubran más de un edificio?

  - ¿Cuánto espacio del piso queda cubierto por cada subred de cliente?

Si la subred cubre un área demasiado extensa, es posible que deba usar otro mecanismo para ubicar a clientes. Sin embargo, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el costo y la complejidad de soluciones basadas en SNMP de terceros.

## Dirección MAC de cliente

Para usar la dirección MAC de un equipo cliente para localizar a una persona que realiza una llamada, necesita conmutadores Ethernet administrados y debe implementar una solución basada en SNMP de terceros que puede descubrir la dirección MAC de los clientes de Lync conectados a (o mediante) dichos conmutadores. La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes. Durante una solicitud de cliente de Lync al Servicio de información de ubicaciones, el Servicio de información de ubicaciones consulta a una aplicación de terceros utilizando la dirección MAC del cliente y devuelve los identificadores de puerto y las direcciones IP de conmutador coincidentes. El Servicio de información de ubicaciones usa luego esta información para consultar su diagrama de cableado de nivel 2 publicado para un registro coincidente y devuelve la ubicación al cliente. Si utiliza esta opción, asegúrese de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.


> [!NOTE]
> Algunas soluciones de SNMP de terceros pueden admitir conmutadores de acceso no administrados; si el conmutador del cliente de Lync no está administrado pero tiene un vínculo superior a un conmutador de distribución administrado, el conmutador administrado puede informar a la aplicación SNMP las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite al Servicio de información de ubicaciones identificar la ubicación del usuario. Sin embargo, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el nivel de chasis del conmutador de acceso, pero no en el nivel de puerto.


