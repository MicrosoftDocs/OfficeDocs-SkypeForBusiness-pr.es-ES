---
title: Planear la Telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Telefonía IP empresarial planificación básica de Skype para Business Server, incluidos los sitios, regiones, vínculos de red entre sitios y estimar el tráfico de uso de la voz.
ms.openlocfilehash: a04c379e3a616a511306db62fd908af26e325418
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>Planear la Telefonía IP empresarial en Skype Empresarial Server 2015
 
Telefonía IP empresarial planificación básica de Skype para Business Server, incluidos los sitios, regiones, vínculos de red entre sitios y estimar el tráfico de uso de la voz.
  
El proceso de implementación de Telefonía IP empresarial depende de la topología existente, infraestructura y la funcionalidad de Telefonía IP empresarial que desea admitir. Los procedimientos necesarios dependerán de las características que seleccione, pero también es preciso tener en cuenta otros aspectos de la planeación que se necesitan realizar en un nivel más específico.
  
En general, hay que tener en cuenta el tipo y la cantidad de sitios que se quiere implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si se quiere proporcionar redundancia y conmutación por error para la función de voz en cada sitio y, asimismo, si se quiere usar el equipo de PBX existente. Hay ciertas consideraciones, como la alta disponibilidad, que se debe considerar al planear Skype para Business Server como un todo. Estas consideraciones se tratan en los distintos temas de esta sección.
  
## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identificar los sitios de la topología donde va a implementar Telefonía IP empresarial y las regiones de la red a la que pertenecen dichos sitios. En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decidir dónde las puertas de enlace se implementará localmente, donde se implementará la aplicación de rama de supervivencia (SBA) y donde puede configurar los troncos SIP (localmente o en el sitio central) a un proveedor de servicios de telefonía de Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe tener en cuenta el uso de ancho de banda que lo esperado en los vínculos de red entre el sitio central y sus sucursales. Si tiene, o va a desplegar resistentes vínculos WAN entre los sitios, se recomienda implementar una puerta de enlace en el sitio de cada sucursal para proporcionar la terminación de marcado interno directo (DID) local para los usuarios de esos sitios. Si tiene vínculos WAN resistentes, pero es probable que se va a restringir el ancho de banda en un vínculo WAN, configurar el control de admisión de llamada de ese vínculo. Si no tiene vínculos WAN resistentes, alojar menos de 1000 usuarios en el sitio de la sucursal y no tiene Skype capacitado local para los administradores de servidores de negocios disponibles, que le recomendamos que se instale un dispositivo de sucursal que sobreviven en el sitio de sucursal. Si aloja entre 1000 y 5000 usuarios en su sitio de sucursal, carecen de una conexión WAN resistente y ha entrenado Skype para los administradores de Business Server está disponibles, que se recomienda implementar un servidor de sucursal que sobreviven con una pequeña puerta de enlace en el sitio de la sucursal. Considere también habilitar omisión de medios en vínculos restringida si tiene un puerta de enlace del mismo nivel que admite la omisión de medios.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimar el uso de voz y el tráfico

El Microsoft Lync Server 2013, la herramienta de planeación utiliza la métrica siguiente para estimar el tráfico de usuarios en cada sitio y el número de puertos que son necesarios para admitir ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
    
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
    
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios. Las puertas de enlace de (RTC) de la red telefónica pública conmutada que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos a puertos como máximo 960. (Hay puertas de enlace aún mayores, pero se utilizan principalmente por proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, características y opciones de Telefonía IP empresarial

Consulte las siguientes secciones para obtener más información acerca de cómo planear la implementación de Telefonía IP empresarial.
  
- [Componentes necesarios para la Telefonía IP empresarial en Skype para Business Server 2015](components-required-for-enterprise-voice.md)
    
- [Plan de conectividad PSTN en Skype para Business Server 2015](pstn-connectivity-0.md)
    
- [Configuración de red para las funciones avanzadas de Telefonía IP empresarial en Skype para Business Server 2015](network-settings-for-advanced-features.md)
    
- [Plan de control de admisión de llamadas en Skype para Business Server 2015](call-admission-control.md)
    
- [Plan de servicios de emergencia en Skype para Business Server 2015](emergency-services.md)
    
- [Planear la omisión de medios en Skype para negocios 2015](media-bypass.md)
    
- [Plan para líneas telefónicas privadas con Skype para negocios 2015](private-telephone-lines.md)
    
- [Plan de enrutamiento basado en ubicación en Skype para negocios 2015](location-based-routing.md)
    
- [Plan de características de administración de llamadas de Skype para negocios 2015](call-management-features.md)
    
- [Plan para la resistencia de la Telefonía IP empresarial en Skype para Business Server 2015](enterprise-voice-resiliency.md)
    

