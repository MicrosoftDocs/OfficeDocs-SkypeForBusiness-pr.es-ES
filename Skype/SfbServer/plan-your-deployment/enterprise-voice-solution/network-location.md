---
title: Definir los elementos de red que se usan para determinar la ubicación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisiones necesarias para la planificación de los componentes de red que va a utilizar para asignar los llamadores a ubicaciones para la implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 2d371b2abfd8e3c871f0d9f49409d2b8169268c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server-2015"></a>Definir los elementos de red que se usan para determinar la ubicación en Skype Empresarial Server 2015
 
Decisiones necesarias para la planificación de los componentes de red que va a utilizar para asignar los llamadores a ubicaciones para la implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
  
Si está configurando su Skype para infraestructura de Business Server para admitir la detección automática del cliente ubicación, primero debe decidir qué red de elementos que se va a usar para asignar los llamadores a ubicaciones. En Skype para Business Server, puede asociar los siguientes elementos de red de capa 2 y capa 3 ubicaciones:
  
- Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)
    
- Puerto del conmutador LLDP (nivel 2)
    
- Identificadores del chasis del conmutador LLDP (nivel 2)
    
- Subredes IP (nivel 3)
    
- Direcciones MAC de cliente (nivel 2)
    
Los elementos de red se enumeran en orden de prioridad. Si un cliente puede encontrarse mediante más de un elemento de red, Skype para Business Server utiliza el orden de prioridad para determinar qué mecanismo utilizar. 
  
En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.
  
> [!IMPORTANT]
> Cuando utiliza elementos de la red para asignar los llamadores a ubicaciones, es de suma importancia mantener la base de datos del servicio de información de ubicación actualizados. Por ejemplo, si agregas o cambias un elemento de red, como cuando agregas un WAP, necesitarás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones. 
  
## <a name="wireless-access-point"></a>Punto de acceso inalámbrico

Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación al usar la dirección BSSID del WAP. Si el cliente es móvil, el WAP indicado puede no ser el más cercano y es incluso posible recoger un WAP en un piso distinto del edificio. Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor **[cerca]** o **[Closeto]** .
  
Este método de ubicación se asume que el BSSID de cada WAP es estático. Sin embargo, si su proveedor WAP utiliza BSSIDs asignado dinámicamente, el BSSID que se obtiene de un WAP podría cambiar (Esto puede ocurrir después de un cambio de configuración de WAP), y los clientes inalámbricos podrían quedar en una situación donde no reciben una ubicación. Para evitar esta posibilidad, es necesario rellenar la información de ubicación servicio base de datos con ERLs para todas las posibles direcciones BSSID utilizados por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Conmutadores y puertos LLDP

Los conmutadores Ethernet administrados que admiten el Protocolo de detección de nivel de vínculo: detección de extremos de medios (LLDP-MED) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puedes asociar las ERL únicamente en el identificador de chasis del conmutador, o bien los puedes asignar en el puerto.
  
> [!NOTE]
> Skype para Business Server admite el uso de LLDP-MED para determinar las ubicaciones sólo de dispositivos Phone Edition de Lync y Skype para clientes empresariales que se ejecutan en Windows 8. Si necesita utilizar datos a nivel de conmutador de capa 2 para determinar la ubicación de otro Skype basados en PC con cable para clientes Business Server, debe utilizar el método de dirección MAC del cliente. 
  
## <a name="subnet"></a>Subred

Subredes IP de capa 3 proporcionan un mecanismo compatible con Skype todos los clientes de Business Server que puede utilizarse para detectar automáticamente la ubicación del cliente. El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes cableados. Pero, antes de decidir usar subredes, necesitarás hacerte las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:
  
- ¿Existe una o más subredes de clientes que cubran varios pisos?
    
- ¿Existe una o más subredes que cubran más de un edificio?
    
- ¿Cuánto espacio del piso queda cubierto por cada subred de cliente?
    
Si la subred cubre un área demasiado extensa, es posible que debas usar otro mecanismo para ubicar a clientes. Pero, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el coste y la complejidad de soluciones basadas en SNMP de terceros.
  
## <a name="client-mac-address"></a>Dirección MAC de cliente

Para utilizar la dirección MAC de un equipo cliente para localizar un llamador, necesita switches Ethernet administrados y debe implementar una solución SNMP de terceros que puede descubrir las direcciones MAC de Skype para clientes de negocios conectados a (o a través de) los modificadores. La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes. Durante un Skype para la solicitud del cliente de la empresa con el servicio de información de la ubicación, el servicio de información de ubicación consulta la aplicación de terceros mediante la dirección MAC del cliente y devuelve cualquier direcciones IP de switch coincidentes e identificadores de puerto. El servicio de información de ubicación utiliza esta información para consultar su diagrama de cableado de capa 2 publicado para un registro coincidente y devuelve la ubicación del cliente. Si utilizas esta opción, asegúrate de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.
  
> [!NOTE]
> Algunas soluciones SNMP de terceros pueden admiten modificadores de acceso no administrado; Si el conmutador que da servicio el Skype para Business client está administrado pero tiene un enlace ascendente a un conmutador de distribución administrada, el switch administrado puede ofrecer información a la aplicación SNMP las direcciones MAC de los clientes conectados al conmutador de acceso. Esta información permite al servicio de información de ubicación identificar la ubicación del usuario. Pero, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el chasis del conmutador de acceso, pero no en el puerto. 
  

