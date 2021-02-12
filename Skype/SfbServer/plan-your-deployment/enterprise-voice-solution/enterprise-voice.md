---
title: Plan for Telefonía IP empresarial in Skype for Business Server
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Telefonía IP empresarial conceptos básicos de planeación en Skype Empresarial Server, incluidos sitios, regiones, vínculos de red entre sitios y estimación del tráfico de uso de voz.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825680"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Plan for Telefonía IP empresarial in Skype for Business Server
 
Telefonía IP empresarial conceptos básicos de planeación en Skype Empresarial Server, incluidos sitios, regiones, vínculos de red entre sitios y estimación del tráfico de uso de voz.
  
El proceso de implementación Telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de Telefonía IP empresarial existentes que desee admitir. Los procedimientos pertinentes dependerán de las características que se eligen, pero también es preciso tener en cuenta otros aspectos de la planeación que deben realizarse en un nivel más específico.
  
En general, debe tenerse en cuenta el tipo y la cantidad de sitios que desea implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si desea proporcionar redundancia y conmutación por error para funcionalidad de voz en cada sitio, y si desea usar el equipo de central de conmutación existente. Hay algunas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planear Skype Empresarial Server en su totalidad. Estas consideraciones se tratan en los temas de la sección según convenga.
  
## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identifique los sitios de la topología en los que implementará Telefonía IP empresarial y las regiones de red a las que pertenecen dichos sitios. En concreto, tenga en cuenta la forma en que proporcionará conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decida dónde se implementarán las puertas de enlace localmente, dónde se implementarán las aplicaciones de sucursal con funciones de supervivencia (SBA) y dónde puede configurar troncos SIP (ya sea localmente o en el sitio central) para un proveedor de servicios de telefonía por Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe tener en cuenta el uso de ancho de banda que espera en los vínculos de red entre el sitio central y sus sitios de sucursal. Si tiene o planea implementar vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de llamada directa a la extensión (DID) local para los usuarios de esos sitios. Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo. Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en su sucursal y no tenga disponibles administradores locales formados de Skype Empresarial Server, le recomendamos que implemente una aplicación de sucursal con funciones de supervivencia en la sucursal. Si hospeda entre 1000 y 5000 usuarios en su sucursal, carece de una conexión WAN resistente y dispone de administradores de Skype Empresarial Server formados, le recomendamos que implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en la sucursal. Considere también la posibilidad de habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admita la omisión de medios.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimación del tráfico y el uso de voz

La Herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para calcular el tráfico de usuarios en cada sitio y el número de puertos necesarios para admitir ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.
> 
> Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.
> 
> Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.
    
A su vez, el número de puertos determina el número de servidores de mediación y puertas de enlace que serán necesarios. Las puertas de enlace de la red telefónica conmutada (RTC) que la mayoría de las organizaciones consideran implementar varían de 2 puertos a hasta 960 puertos. (Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, características y opciones de Telefonía IP empresarial

Vea las siguientes secciones para obtener más información sobre la planeación de la Telefonía IP empresarial implementación.
  
- [Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server](components-required-for-enterprise-voice.md)
    
- [Planear la conectividad con RTC en Skype Empresarial Server](pstn-connectivity-0.md)
    
- [Configuración de red para las características de Telefonía IP empresarial avanzadas en Skype Empresarial Server](network-settings-for-advanced-features.md)
    
- [Planear el control de admisión de llamadas en Skype Empresarial Server](call-admission-control.md)
    
- [Planear los servicios de emergencia en Skype Empresarial Server](emergency-services.md)
    
- [Planear la omisión de medios en Skype Empresarial](media-bypass.md)
    
- [Planificar líneas de teléfono privadas con Skype Empresarial](private-telephone-lines.md)
    
- [Plan for Location-Based Routing in Skype for Business](location-based-routing.md)
    
- [Planear las características de administración de llamadas en Skype Empresarial](call-management-features.md)
    
- [Planeación de Telefonía IP empresarial resistencia en Skype Empresarial Server](enterprise-voice-resiliency.md)
    

