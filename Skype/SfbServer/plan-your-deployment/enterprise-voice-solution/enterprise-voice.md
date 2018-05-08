---
title: Planear la Telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise Voice planeación conceptos básicos en Skype Business Server, incluidos los sitios, áreas, vínculos de red entre sitios y estimar el tráfico de uso de voz.
ms.openlocfilehash: f1bd8f2f8514f34390cd085bd1407894e9788620
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>Planear la Telefonía IP empresarial en Skype Empresarial Server 2015
 
Enterprise Voice planeación conceptos básicos en Skype Business Server, incluidos los sitios, áreas, vínculos de red entre sitios y estimar el tráfico de uso de voz.
  
El proceso de implementación de Enterprise Voice depende de la topología existente, infraestructura y la funcionalidad de Enterprise Voice que desea admitir. Los procedimientos necesarios dependerán de las características que seleccione, pero también es preciso tener en cuenta otros aspectos de la planeación que se necesitan realizar en un nivel más específico.
  
En general, hay que tener en cuenta el tipo y la cantidad de sitios que se quiere implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si se quiere proporcionar redundancia y conmutación por error para la función de voz en cada sitio y, asimismo, si se quiere usar el equipo de PBX existente. Hay algunas consideraciones, como una alta disponibilidad, que debe tener en cuenta al planear Skype para Business Server como un todo. Estas consideraciones se tratan en los distintos temas de esta sección.
  
## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identifique los sitios de la topología donde va a implementar Enterprise Voice y las regiones de red al que pertenecen esos sitios. En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decidir dónde las puertas de enlace se implementará localmente, donde va a implementar aplicaciones de sucursal con funciones de supervivencia (SBA) y donde puede configurar troncos SIP (localmente o en el sitio central) a un proveedor de servicios de telefonía de Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe tener en cuenta el uso de ancho de banda que se esperaba en los vínculos de red entre el sitio central y sus sitios de sucursal. Si tiene, o va a implementar, resistentes vínculos WAN entre sitios, se recomienda que implemente una puerta de enlace en cada sitio de sucursal para proporcionar terminación local directa DID (llamada) para los usuarios de esos sitios. Si tiene vínculos WAN resistentes, pero es probable que se va a restringir el ancho de banda en un vínculo WAN, configuración de control de admisión de llamadas para ese vínculo. Si no tienen vínculos WAN resistentes, hospedar menos de 1000 usuarios en su sitio de sucursal y no tienen Skype capacitado local empresarial para administradores de servidor disponibles, que se recomienda implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. Si el host entre 1000 y 5000 usuarios en su sitio de sucursal, carecen de una conexión WAN resistente y han formación Skype empresarial para administradores de servidor disponibles, que se recomienda implementar un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en el sitio de sucursal. Tenga en cuenta también Habilitar desvío de medios en vínculos limitada si dispone de un puerta de enlace del mismo nivel que admite el desvío de medios.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimar el uso de voz y el tráfico

El Microsoft Lync Server 2013, herramienta de planeación utiliza la métrica siguiente para calcular el tráfico de usuario en cada sitio y el número de puertos que se requieren para admitir dicho tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
    
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
    
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios. Las puertas de enlace de (RTC) de la red telefónica conmutada pública que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos para los puertos de 960 como máximo. (Hay puertas de enlace incluso más grandes, pero las usan principalmente por proveedores de servicios de telefonía.)
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, características y opciones de Enterprise Voice

Consulte las siguientes secciones para obtener más información acerca de cómo planear la implementación de Enterprise Voice.
  
- [Componentes necesarios para Enterprise Voice en Skype para Business Server 2015](components-required-for-enterprise-voice.md)
    
- [Plan para la conectividad de RTC en Skype para Business Server 2015](pstn-connectivity-0.md)
    
- [Configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server 2015](network-settings-for-advanced-features.md)
    
- [Planeación de control de admisión de llamadas en Skype para Business Server 2015](call-admission-control.md)
    
- [Planeación de servicios de emergencia en Skype para Business Server 2015](emergency-services.md)
    
- [Planeación de desvío de medios en Skype para profesionales de 2015](media-bypass.md)
    
- [Planeación de líneas de teléfono privadas con Skype para profesionales de 2015](private-telephone-lines.md)
    
- [Planeación de enrutamiento basado en ubicación de Skype para profesionales de 2015](location-based-routing.md)
    
- [Planeación de características de administración de llamadas de Skype para profesionales de 2015](call-management-features.md)
    
- [Plan para la resistencia de Enterprise Voice en Skype para Business Server 2015](enterprise-voice-resiliency.md)
    

