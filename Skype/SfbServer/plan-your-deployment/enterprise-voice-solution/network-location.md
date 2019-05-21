---
title: Definir los elementos de red que se usan para determinar la ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisiones necesarias para planear qué componentes de red usará para asignar las personas que llaman a ubicaciones para la implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a68f1517d038f82e62a7aca3ef909e4e67d25e4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276694"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir los elementos de red que se usan para determinar la ubicación en Skype empresarial Server
 
Decisiones necesarias para planear qué componentes de red usará para asignar las personas que llaman a ubicaciones para la implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
  
Si va a configurar la infraestructura de Skype empresarial Server para que admita la detección automática de la ubicación del cliente, primero debe decidir qué elementos de la red va a usar para asignar las personas que llaman a las ubicaciones. En Skype empresarial Server, puede asociar los siguientes elementos de red de la capa 2 y de la capa 3 con ubicaciones:
  
- Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)
    
- Puerto del conmutador LLDP (nivel 2)
    
- Identificadores del chasis del conmutador LLDP (nivel 2)
    
- Subredes IP (nivel 3)
    
- Direcciones MAC de cliente (nivel 2)
    
Los elementos de red se enumeran en orden de prioridad. Si un cliente puede encontrarse usando más de un elemento de red, Skype empresarial Server usa el orden de prioridad para determinar qué mecanismo usar. 
  
En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.
  
> [!IMPORTANT]
> Al usar elementos de red para asignar las personas que llaman a ubicaciones, es muy importante que mantenga actualizada la base de datos del servicio de información de ubicación. Por ejemplo, si agregas o cambias un elemento de red, como cuando agregas un WAP, necesitarás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones. 
  
## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación al usar la dirección BSSID del WAP. Si el cliente está en itinerancia, la WAP indicada puede no ser la más cercana, y incluso es posible que se recoja un WAP que se encuentre en un piso diferente del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor **[Near]** o **[closeto]** .
  
Este método de ubicación supone que el BSSID de cada WAP es estático. Sin embargo, si su proveedor WAP usa BSSIDs asignados dinámicamente, los BSSID que se obtengan de un WAP podrían cambiar (esto puede ocurrir después de un cambio de configuración WAP), y los clientes inalámbricos podrían permanecer en una situación en la que no reciban una ubicación. Para evitar esta posibilidad, debe rellenar la base de datos de servicios de información de ubicación con ERLs para todas las direcciones BSSID posibles que cada WAP usa. 
  
## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten el Protocolo de detección de nivel de vínculo: detección de extremos de medios (LLDP-MED) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puedes asociar las ERL únicamente en el identificador de chasis del conmutador, o bien los puedes asignar en el puerto.
  
> [!NOTE]
> Skype empresarial Server admite el uso de LLDP-MED para determinar las ubicaciones de los dispositivos Lync Phone Edition y de los clientes de Skype empresarial que se ejecutan en Windows 8. Si necesita usar datos de capa 2 a nivel de conmutador para determinar la ubicación de otros clientes con cable de Skype empresarial Server, debe usar el método de dirección MAC del cliente. 
  
## <a name="subnet"></a>Subred

Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Skype empresarial Server que pueden usarse para detectar automáticamente la ubicación de los clientes. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes cableados. Pero, antes de decidir usar subredes, necesitarás hacerte las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:
  
- ¿Existe una o más subredes de clientes que cubran varios pisos?
    
- ¿Existe una o más subredes que cubran más de un edificio?
    
- ¿Cuánto espacio del piso queda cubierto por cada subred de cliente?
    
Si la subred cubre un área demasiado extensa, es posible que debas usar otro mecanismo para ubicar a clientes. Pero, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el coste y la complejidad de soluciones basadas en SNMP de terceros.
  
## <a name="client-mac-address"></a>Dirección MAC de cliente

Para usar la dirección MAC de un equipo cliente para ubicar una persona que llama, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda descubrir las direcciones MAC de los clientes de Skype empresarial conectados a esos conmutadores (o a través de ellos). La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes. Durante la solicitud de un cliente de Skype empresarial al servicio de información de ubicación, el servicio de información de ubicación consulta la aplicación de terceros usando la dirección MAC del cliente y, a continuación, devuelve las direcciones IP y los identificadores de puerto que coincidan. El servicio de información de ubicación usa esta información para consultar sus Wiremap de capa 2 publicadas y devuelve la ubicación al cliente. Si utilizas esta opción, asegúrate de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.
  
> [!NOTE]
> Algunas soluciones SNMP de terceros pueden admitir modificadores de acceso no administrados; Si el modificador que ofrece servicio al cliente de Skype empresarial no está administrado pero tiene un vínculo superior a un conmutador de distribución administrada, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite que el servicio de información de ubicación identifique la ubicación del usuario. Pero, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el chasis del conmutador de acceso, pero no en el puerto. 
  

