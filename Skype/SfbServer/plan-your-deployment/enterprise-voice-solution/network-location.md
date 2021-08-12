---
title: Definir los elementos de red usados para determinar la ubicación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisiones necesarias para planear los componentes de red que usará para asignar autores de llamadas a ubicaciones para la implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: fba8617643ac730d56f24e318a48cdb218b523cdceaa0cb810cc01c6c9d8a753
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281683"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir los elementos de red usados para determinar la ubicación en Skype Empresarial Server
 
Decisiones necesarias para planear los componentes de red que usará para asignar autores de llamadas a ubicaciones para la implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
  
Si va a configurar la infraestructura Skype Empresarial Server para admitir la detección automática de ubicaciones de cliente, primero debe decidir qué elementos de red va a usar para asignar llamadas a ubicaciones. En Skype Empresarial Server, puede asociar los siguientes elementos de red de capa 2 y 3 con ubicaciones:
  
- Direcciones de identificación de conjunto de servicios básicos (BSSID) de punto de acceso inalámbrico (WAP) (capa 2)
    
- Puerto de conmutador LLDP (capa 2)
    
- IDs de chasis de conmutador LLDP (capa 2)
    
- Subredes IP (capa 3)
    
- Direcciones MAC de cliente (capa 2)
    
Los elementos de red se enumeran en orden de prioridad. Si un cliente se puede encontrar mediante el uso de más de un elemento de red, Skype Empresarial Server el orden de prioridad para determinar qué mecanismo usar. 
  
En las secciones siguientes se proporcionan más detalles para usar cada elemento de red.
  
> [!IMPORTANT]
> Al usar elementos de red para asignar personas que llaman a ubicaciones, es de suma importancia mantener actualizada la base de datos del servicio de información de ubicación. Por ejemplo, si agrega o cambia un elemento de red, como agregar un WAP, debe eliminar la entrada antigua y agregar la nueva entrada en la base de datos de ubicación. 
  
## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de forma inalámbrica, la solicitud de ubicación usa la dirección BSSID del WAP para determinar su ubicación. Si el cliente está en itinerancia, el WAP indicado puede no ser el más cercano e incluso es posible elegir un WAP que se encuentra en un piso diferente del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor **[Near]** o **[Closeto].**
  
Este método de ubicación supone que el BSSID de cada WAP es estático. Sin embargo, si el proveedor wap usa SSID asignados dinámicamente, el BSSID que se obtiene de un WAP podría cambiar (esto puede ocurrir después de un cambio de configuración wap) y los clientes inalámbricos podrían quedar en una situación en la que no reciben una ubicación. Para evitar esta posibilidad, debe rellenar la base de datos del servicio de información de ubicación con LASR para todas las direcciones BSSID posibles usadas por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Puertos y conmutadores LLDP

Los conmutadores Ethernet administrados que admiten la detección de la capa de vínculos Protocol-Media Endpoint Discover (LLDP-MED) pueden anunciar su identidad y la información de puerto a clientes compatibles con LLDP-MED, que luego se pueden consultar en la base de datos de ubicación para proporcionar la ubicación del dispositivo. Puede asociar las ERL únicamente en el identificador del chasis del conmutador o puede asignarlas al nivel de puerto.
  
> [!NOTE]
> Skype Empresarial Server admite el uso de LLDP-MED para determinar ubicaciones solo de dispositivos Lync Teléfono Edition y clientes Skype Empresarial que se ejecutan en Windows 8. Si necesita usar datos de nivel de conmutador de nivel 2 para determinar la ubicación de otros clientes de Skype Empresarial Server pc con cable, debe usar el método de dirección MAC del cliente. 
  
## <a name="subnet"></a>Subred

Las subredes IP de la capa 3 proporcionan un mecanismo compatible con todos los Skype Empresarial Server que se pueden usar para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más fácil para configurar y administrar clientes con cable. Sin embargo, antes de decidir usar subredes, use las siguientes preguntas para determinar si la especificidad de ubicación de la subred es lo suficientemente buena como para localizar un cliente con precisión:
  
- ¿Una o más subredes de cliente cubren varios pisos?
    
- ¿Una o más subredes cubren más de un edificio?
    
- ¿Cuánto espacio de planta cubre cada subred de cliente?
    
Si la subred cubre un área demasiado amplia, es posible que deba usar otro mecanismo para localizar clientes. Sin embargo, si es práctico, se recomienda a los clientes reorganizar sus subredes IP para cumplir los requisitos de especificidad de ubicación de ERL en lugar de incurrir en el costo y la complejidad de las soluciones basadas en SNMP de terceros.
  
## <a name="client-mac-address"></a>Dirección MAC del cliente

Para usar la dirección MAC de un equipo cliente para localizar a un autor de la llamada, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda detectar las direcciones MAC de los clientes de Skype Empresarial conectados a (o a través) de dichos conmutadores. La solución SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de punto de conexión conectadas a cada puerto y obtiene los correspondientes IDs de puerto. Durante la solicitud de un cliente de Skype Empresarial al servicio de información de ubicación, el servicio de información de ubicación consulta la aplicación de terceros mediante la dirección MAC del cliente y, a continuación, devuelve las direcciones IP del conmutador e IDs de puerto que coincidan. El servicio de información de ubicación usa esta información para consultar el mapa de conexión de la capa 2 publicado para obtener un registro que coincida y devuelve la ubicación al cliente. Si usa esta opción, asegúrese de que los identificadores de puerto de conmutador sean coherentes entre la aplicación SNMP y los registros de base de datos de ubicación publicados.
  
> [!NOTE]
> Algunas soluciones SNMP de terceros pueden admitir conmutadores de acceso no administrados; si el modificador que da servicio al cliente de Skype Empresarial no está administrado pero tiene un vínculo ascendente a un conmutador de distribución administrado, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite al servicio de información de ubicación identificar la ubicación del usuario. Sin embargo, es posible asignar un solo ERL a todos los puertos del conmutador no administrado, por lo que la especificidad de la ubicación solo está disponible en el nivel de chasis del conmutador de acceso, no en el nivel de puerto. 
  

