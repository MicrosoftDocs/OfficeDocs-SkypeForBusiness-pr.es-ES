---
title: Definir los elementos de red que se utiliza para determinar la ubicación de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisiones necesarias para planear qué componentes de red que va a usar para asignar los autores de llamadas a las ubicaciones para la implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 4cab36efdf0f4bcfbf3834e9c077558610655e3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882309"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir los elementos de red que se utiliza para determinar la ubicación de Skype para Business Server
 
Decisiones necesarias para planear qué componentes de red que va a usar para asignar los autores de llamadas a las ubicaciones para la implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
  
Si está configurando su Skype para infraestructura de Business Server para admitir la detección de ubicación automático de los clientes, primero debe decidir qué red elementos que se va a usar para asignar los autores de llamadas a ubicaciones. En Skype para Business Server, puede asociar los siguientes elementos de red de nivel 2 y nivel 3 con ubicaciones:
  
- Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)
    
- Puerto del conmutador LLDP (nivel 2)
    
- Identificadores del chasis del conmutador LLDP (nivel 2)
    
- Subredes IP (nivel 3)
    
- Direcciones MAC de cliente (nivel 2)
    
Los elementos de red se enumeran en orden de prioridad. Si un cliente puede estar ubicado mediante el uso de más de un elemento de red, Skype para Business Server usa el orden de prioridad para determinar qué mecanismo de. 
  
En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.
  
> [!IMPORTANT]
> Al usar elementos de red para asignar los autores de llamadas a ubicaciones, es de máxima importancia que mantener la base de datos de servicio de información de ubicación actualizado. Por ejemplo, si agregas o cambias un elemento de red, como cuando agregas un WAP, necesitarás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones. 
  
## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación al usar la dirección BSSID del WAP. Si el cliente es móvil, el WAP indicado puede no ser el más cercano e incluso es posible recoger un WAP que se encuentra en un piso distinto del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor **[cerca]** o **[cerrar]** .
  
Este método de ubicación se da por supuesto que BSSID de cada WAP es estático. Sin embargo, si su proveedor de WAP usa BSSIDs asignados dinámicamente, BSSID que se obtiene de un WAP podría cambiar (Esto puede ocurrir después de un cambio de configuración de WAP) y los clientes inalámbricos podrían quedar en una situación donde no reciben una ubicación. Para evitar esta posibilidad, debe rellenar la información de ubicación base de datos con Erl para todas las direcciones BSSID posibles usado por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten el Protocolo de detección de nivel de vínculo: detección de extremos de medios (LLDP-MED) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puedes asociar las ERL únicamente en el identificador de chasis del conmutador, o bien los puedes asignar en el puerto.
  
> [!NOTE]
> Skype para Business Server admite el uso LLDP-MED para determinar las ubicaciones sólo de los dispositivos de Lync Phone Edition y Skype para clientes empresariales que se ejecutan en Windows 8. Si necesita usar datos a nivel de conmutador de nivel 2 para determinar la ubicación de otro por cable Skype basados en PC para que los clientes de Business Server, debe usar el método de dirección MAC del cliente. 
  
## <a name="subnet"></a>Subred

Subredes IP de capa 3 proporcionan un mecanismo compatible con todos los Skype para los clientes de Business Server que se pueden usar para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes cableados. Pero, antes de decidir usar subredes, necesitarás hacerte las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:
  
- ¿Existe una o más subredes de clientes que cubran varios pisos?
    
- ¿Existe una o más subredes que cubran más de un edificio?
    
- ¿Cuánto espacio del piso queda cubierto por cada subred de cliente?
    
Si la subred cubre un área demasiado extensa, es posible que debas usar otro mecanismo para ubicar a clientes. Pero, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el coste y la complejidad de soluciones basadas en SNMP de terceros.
  
## <a name="client-mac-address"></a>Dirección MAC de cliente

Para usar la dirección MAC de un equipo cliente para localizar un autor de la llamada, necesita los conmutadores Ethernet administrados, y debe implementar una solución SNMP de terceros que puede detectar las direcciones MAC de Skype para clientes empresariales conectados a (o a través de) los modificadores. La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes. Durante una Skype para la solicitud del cliente de negocio al servicio de información de ubicación, el servicio de información de ubicación de las consultas de la aplicación de terceros mediante el uso de la dirección MAC del cliente y, a continuación, devuelve las direcciones IP de modificador coincidentes y los identificadores de puerto. El servicio de información de ubicación usa esta información para consultar su diagrama de cableado de capa 2 publicado para un registro coincidente y devuelve la ubicación para el cliente. Si utilizas esta opción, asegúrate de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.
  
> [!NOTE]
> Algunas soluciones SNMP de terceros pueden admitir los modificadores de acceso no administrado; Si el conmutador que los servicios el Skype para clientes empresariales es no administrado pero tiene un enlace ascendente a un conmutador de distribución administrada, el modificador administrado puede informar de vuelta a la aplicación SNMP las direcciones MAC de los clientes conectados al modificador de acceso. Esta información habilita el servicio de información de ubicación identificar la ubicación del usuario. Pero, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el chasis del conmutador de acceso, pero no en el puerto. 
  

