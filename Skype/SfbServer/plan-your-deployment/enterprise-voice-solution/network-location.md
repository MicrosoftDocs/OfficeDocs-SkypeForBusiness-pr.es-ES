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
description: Decisiones necesarias para planear qué componentes de red usará para asignar a los autores de llamadas ubicaciones para la implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813640"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir los elementos de red usados para determinar la ubicación en Skype Empresarial Server
 
Decisiones necesarias para planear qué componentes de red usará para asignar a las personas que llaman a ubicaciones para la implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
  
Si va a configurar la infraestructura de Skype Empresarial Server para admitir la detección automática de ubicación de clientes, primero debe decidir qué elementos de red va a usar para asignar a las personas que llaman a ubicaciones. En Skype Empresarial Server, puede asociar los siguientes elementos de red de capa 2 y 3 con ubicaciones:
  
- Direcciones de identificación del conjunto de servicios básicos (BSSID) del punto de acceso inalámbrico (WAP) (capa 2)
    
- Puerto de conmutador LLDP (capa 2)
    
- IDs del chasis del conmutador LLDP (capa 2)
    
- Subredes IP (capa 3)
    
- Direcciones MAC de cliente (capa 2)
    
Los elementos de red se enumeran en orden de prioridad. Si un cliente puede encontrarse con más de un elemento de red, Skype Empresarial Server usa el orden de prioridad para determinar qué mecanismo usar. 
  
En las secciones siguientes se proporcionan más detalles para usar cada elemento de red.
  
> [!IMPORTANT]
> Cuando se usan elementos de red para asignar autores de llamadas a ubicaciones, es muy importante mantener actualizada la base de datos del servicio de información de ubicaciones. Por ejemplo, si agregas o cambias un elemento de red, como agregar un WAP, debes eliminar la entrada antigua y agregar la nueva entrada en la base de datos de ubicación. 
  
## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de forma inalámbrica, la solicitud de ubicación usa la dirección BSSID del WAP para determinar su ubicación. Si el cliente está en itinerancia, es posible que el WAP indicado no sea el más cercano e incluso es posible seleccionar un WAP que se encuentra en una planta diferente del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor **[Near]** o **[Closeto].**
  
Este método de ubicación supone que el BSSID de cada WAP es estático. Sin embargo, si tu proveedor wap usa SSID asignados dinámicamente, el BSSID que se obtiene de un WAP podría cambiar (esto puede ocurrir después de un cambio de configuración WAP) y los clientes inalámbricos podrían quedar en una situación en la que no reciben una ubicación. Para evitar esta posibilidad, debe rellenar la base de datos del servicio de información de ubicación con ERL para todas las direcciones BSSID posibles que usa cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) pueden anunciar su identidad y su información de puerto a clientes compatibles con LLDP-MED, que luego se pueden consultar en la base de datos de ubicación para proporcionar la ubicación del dispositivo. Puede asociar ERL únicamente en el identificador del chasis del conmutador o puede asignarlas al nivel de puerto.
  
> [!NOTE]
> Skype Empresarial Server admite el uso de LLDP-MED para determinar ubicaciones solo de dispositivos Lync Phone Edition y clientes de Skype Empresarial que se ejecutan en Windows 8. Si necesita usar datos de nivel de conmutador 2 para determinar la ubicación de otros clientes de Skype Empresarial Server basados en PC con cable, debe usar el método de dirección MAC de cliente. 
  
## <a name="subnet"></a>Subred

Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Skype Empresarial Server que se pueden usar para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes con cable. Sin embargo, antes de decidir usar subredes, use las siguientes preguntas para determinar si la especificidad de ubicación de la subred es lo suficientemente adecuada para localizar con precisión un cliente:
  
- ¿Una o más subredes de cliente cubren varios piso?
    
- ¿Una o más subredes cubren más de un edificio?
    
- ¿Cuánto espacio de planta cubre cada subred de cliente?
    
Si la subred cubre un área demasiado amplia, es posible que deba usar otro mecanismo para localizar clientes. Sin embargo, si en absoluto es práctico, recomendamos que los clientes reorganice su subred IP para cumplir los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el costo y la complejidad de las soluciones basadas en SNMP de terceros.
  
## <a name="client-mac-address"></a>Dirección MAC del cliente

Para usar la dirección MAC de un equipo cliente para localizar al autor de la llamada, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda detectar las direcciones MAC de los clientes de Skype Empresarial conectados a (o a través) de esos conmutadores. La solución SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de extremo conectadas a cada puerto y obtiene los correspondientes IDs de puerto. Durante la solicitud de un cliente de Skype Empresarial al servicio de información de ubicación, el servicio de información de ubicación consulta la aplicación de terceros mediante la dirección MAC del cliente y, a continuación, devuelve cualquier dirección IP de conmutador e IDs de puerto que coincidan. El servicio de información de ubicación usa esta información para consultar el mapa de cableado de capa 2 publicado para obtener un registro que coincida y devuelve la ubicación al cliente. Si usa esta opción, asegúrese de que los identificadores de puerto de conmutador sean coherentes entre la aplicación SNMP y los registros de base de datos de ubicación publicados.
  
> [!NOTE]
> Algunas soluciones SNMP de terceros pueden admitir conmutadores de acceso no administrados; si el conmutador que da servicio al cliente de Skype Empresarial no está administrado pero tiene un vínculo ascendente a un conmutador de distribución administrado, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite al servicio de información de ubicación identificar la ubicación del usuario. Sin embargo, solo es posible asignar un único ERL a todos los puertos del conmutador no administrado, por lo que la especificidad de la ubicación solo está disponible en el nivel de chasis del conmutador de acceso, no en el nivel de puerto. 
  

