---
title: Planear la telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Conceptos básicos de la planificación de telefonía IP empresarial en Skype empresarial Server, incluidos los sitios, las regiones, los vínculos de red entre los sitios y la estimación del tráfico de uso de voz.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802900"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planear la telefonía IP empresarial en Skype empresarial Server
 
Conceptos básicos de la planificación de telefonía IP empresarial en Skype empresarial Server, incluidos los sitios, las regiones, los vínculos de red entre los sitios y la estimación del tráfico de uso de voz.
  
El proceso de implementación de telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de telefonía IP de empresa que desee admitir. Los procedimientos necesarios dependerán de las características que seleccione, pero también es preciso tener en cuenta otros aspectos de la planeación que se necesitan realizar en un nivel más específico.
  
En general, hay que tener en cuenta el tipo y la cantidad de sitios que se quiere implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si se quiere proporcionar redundancia y conmutación por error para la función de voz en cada sitio y, asimismo, si se quiere usar el equipo de PBX existente. Hay ciertas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planificar Skype empresarial Server como un todo. Estas consideraciones se tratan en los distintos temas de esta sección.
  
## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identifique los sitios de su topología en los que va a implementar Enterprise Voice y las regiones de red a las que pertenecen dichos sitios. En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decidir dónde se implementarán las puertas de enlace de forma local, donde se implementarán los dispositivos de sucursal (SBAs) supervivientes, y donde puede configurar los troncos SIP (ya sea de forma local o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe considerar el uso de ancho de banda que espera en los vínculos de red entre su sitio central y sus sitios de sucursales. Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado directo local (sí) para los usuarios de esos sitios. Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo. Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de la sucursal y no tiene los administradores de servidores de Skype para empresas capacitados en el nivel local, le recomendamos que implemente una aplicación de mayor supervivencia en el sitio de la sucursal. Si se aloja entre usuarios de 1000 y 5000 en su sitio de sucursal, carece de una conexión WAN resistente y tiene disponibles los administradores de servidores de Skype para empresas, le recomendamos que implemente un servidor de sucursal con una pequeña puerta de enlace en el sitio de la sucursal. También debe considerar habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimar el uso de voz y el tráfico

La herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para estimar el tráfico de los usuarios en cada sitio y el número de puertos necesarios para ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
> 
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
> 
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos, a su vez, determina la cantidad de servidores de mediación y puertas de enlace que se requerirán. Las puertas de enlace de red de telefonía pública conmutada (RTC) que la mayoría de las organizaciones consideran implementar intervalos de tamaño desde dos puertos hasta un máximo de 960 puertos. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, características y opciones de telefonía IP empresarial

Consulte las siguientes secciones para obtener más información sobre cómo planear la implementación de telefonía IP empresarial.
  
- [Componentes necesarios para la telefonía IP empresarial en Skype empresarial Server](components-required-for-enterprise-voice.md)
    
- [Planear la conectividad RTC en Skype empresarial Server](pstn-connectivity-0.md)
    
- [Configuración de red para las características avanzadas de telefonía empresarial de Skype empresarial Server](network-settings-for-advanced-features.md)
    
- [Plan para el control de admisión de llamadas en Skype empresarial Server](call-admission-control.md)
    
- [Planear los servicios de emergencia en Skype empresarial Server](emergency-services.md)
    
- [Plan de omisión de multimedia en Skype empresarial](media-bypass.md)
    
- [Planear líneas telefónicas privadas con Skype empresarial](private-telephone-lines.md)
    
- [Planear el enrutamiento basado en la ubicación en Skype empresarial](location-based-routing.md)
    
- [Planear las características de administración de llamadas en Skype empresarial](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

