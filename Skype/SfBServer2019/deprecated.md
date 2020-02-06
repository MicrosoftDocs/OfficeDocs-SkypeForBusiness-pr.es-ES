---
title: Qué es en desuso de Skype empresarial Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han eliminado de Skype empresarial Server 2019.'
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813988"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Qué es en desuso de Skype empresarial Server 2019

Obtenga más información sobre las características y funcionalidades que ya no se usan en Skype empresarial Server 2019. Para obtener información sobre las nuevas características de Skype empresarial Server 2019, consulte [novedades de Skype empresarial server 2019](whats-new.md).

Algunas características desacentuadas están incluidas en Skype empresarial Server 2019 por compatibilidad con versiones anteriores del producto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Características desusadas en Skype empresarial Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Puertas de enlace XMPP para Skype empresarial Server

Skype empresarial Server 2015 y sus antecesores le permiten configurar un proxy protocolo de presencia y mensajería extensible (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo front-end. Esta funcionalidad ya no está disponible en Skype empresarial Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para Skype empresarial Server

El servidor de chat persistente es un rol opcional que permite que varios usuarios de su organización participen en las conversaciones del salón de chat que se mantienen a lo largo del tiempo. El chat persistente no se puede implementar con Skype empresarial Server 2019. Este rol de servidor se ha quitado de Topology Builder, así como del código. 

La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Reflejo de SQL para Skype empresarial Server

No se puede implementar la creación de reflejos de SQL con Skype empresarial Server 2019. Aún se admiten otras opciones para ofrecer una alta disponibilidad y recuperación ante desastres y debe elegir entre ellas. Consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.

### <a name="in-place-upgrades"></a>Actualizaciones locales 

Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. La actualización en paralelo y la coexistencia son compatibles, consulte [migración a Skype empresarial Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.

### <a name="mobility-service-mcx"></a>Servicio de movilidad (MCX)

El soporte de servicio de movilidad usado por clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Esto fue anunciado anteriormente en Skype empresarial Server 2015.

Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.

Para obtener más información, consulte [plan de movilidad para Skype empresarial Server](../SfbServer/plan-your-deployment/mobility.md) y la [comparación de características de cliente móvil para Skype empresarial](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Herramientas

Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype empresarial Server 2019:

- Calculadora de planeamiento de capacidad de Skype Empresarial Server
- Herramientas de depuración de Skype empresarial Server
- Herramientas del kit de recursos de Skype empresarial Server (se quitarán algunas herramientas)
    - Call Parkometer (Estacionamiento de llamadas)
    - Consola de búsqueda de usuarios
    - Migración del anuncio de número no asignado

Las siguientes herramientas no son compatibles con Skype empresarial Server 2019:

- Metodología de calidad de las llamadas (pero no panel de calidad de las llamadas)
- Cuadro de mandos de metodología de llamadas de Microsoft, v 1.5
- Herramienta de planeación de Skype Empresarial Server 2015
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Vea también

[Novedades de Skype empresarial Server 2019](whats-new.md)

[Migrar la federación XMPP](migration/migrating-xmpp-federation.md)
