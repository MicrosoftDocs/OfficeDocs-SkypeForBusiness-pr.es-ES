---
title: Lo que está en desuso Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han quitado de Skype Empresarial Server 2019.'
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282473"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Lo que está en desuso Skype Empresarial Server 2019

Obtenga información sobre las características y funcionalidades que están en desuso en Skype Empresarial Server 2019. Para obtener información sobre las nuevas características de Skype Empresarial Server 2019, vea [What's in Skype Empresarial Server 2019](whats-new.md).

Algunas características no enfatizadas se incluyen en Skype Empresarial Server 2019 por compatibilidad con versiones anteriores del producto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Características en desuso en Skype Empresarial Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Puertas de enlace XMPP para Skype Empresarial Server

Skype Empresarial Server 2015 y sus predecesoras le permitieron configurar un proxy de Protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o grupo de servidores front-end. Esta funcionalidad ya no está disponible en Skype Empresarial Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para Skype Empresarial Server

El servidor de chat persistente es un rol opcional que permite a varios usuarios de la organización participar en conversaciones de salón de chat que persisten con el tiempo. El chat persistente no se puede implementar con Skype Empresarial Server 2019. Este rol de servidor se quita del Generador de topologías, así como del código. 

La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Creación de reflejos para Skype Empresarial Server

SQL La creación de reflejos no se puede implementar Skype Empresarial Server 2019. Todavía se admiten otras opciones para proporcionar alta disponibilidad y recuperación ante desastres y debe elegir entre ellas. Consulte [Plan for high availability and disaster recovery in Skype Empresarial Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.

### <a name="in-place-upgrades"></a>Actualizaciones locales 

Las actualizaciones locales estaban disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Se admite la actualización y la coexistencia en paralelo, vea [Migración a Skype Empresarial Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.

### <a name="mobility-service-mcx"></a>Servicio de movilidad (Mcx)

La compatibilidad con el servicio de movilidad que usan los clientes móviles heredados ya no está disponible Skype Empresarial Server 2019. Esto se anunció anteriormente en Skype Empresarial Server 2015.

Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen Mcx tendrán que actualizar a un cliente actual.

Para obtener más información, vea [Plan for Mobility for Skype Empresarial Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for [Skype Empresarial](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Herramientas

Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype Empresarial Server 2019:

- Calculadora de planeamiento de capacidad de Skype Empresarial Server
- Skype Empresarial Server Herramientas de depuración
- Skype Empresarial Server Herramientas del kit de recursos (se quitarán algunas herramientas)
    - Parkometer de llamadas
    - Consola de usuario de búsqueda
    - Número sinsignado Migración de anuncios

Las siguientes herramientas no son compatibles con Skype Empresarial Server 2019:

- Metodología de calidad de llamadas (pero no panel de calidad de llamadas)
- Cuadro de mandos de metodología de calidad de llamadas de Microsoft, v1.5
- Skype Empresarial Server de planeación de 2015
- Skype Empresarial Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Consulte también

[Novedades de Skype Empresarial Server 2019](whats-new.md)

[Migrar la federación XMPP](migration/migrating-xmpp-federation.md)
