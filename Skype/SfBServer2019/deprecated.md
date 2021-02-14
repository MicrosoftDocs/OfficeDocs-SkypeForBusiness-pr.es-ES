---
title: Qué está en desuso de Skype Empresarial Server 2019
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
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808730"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Qué está en desuso de Skype Empresarial Server 2019

Obtenga información sobre las características y funciones que están en desuso en Skype Empresarial Server 2019. Para obtener información sobre las nuevas características de Skype Empresarial Server 2019, consulte [What's in Skype for Business Server 2019](whats-new.md).

Algunas características que no se destacan se incluyen en Skype Empresarial Server 2019 para la compatibilidad con versiones anteriores del producto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Características en desuso en Skype Empresarial Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Puertas de enlace XMPP para Skype Empresarial Server

Skype Empresarial Server 2015 y sus predecesores le permitían configurar un proxy del Protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o grupo de servidores front-end. Esta funcionalidad ya no está disponible en Skype Empresarial Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para Skype Empresarial Server

El servidor de chat persistente es un rol opcional que permite a varios usuarios de su organización participar en conversaciones de salón de chat que persisten con el tiempo. El chat persistente no se puede implementar con Skype Empresarial Server 2019. Este rol de servidor se ha quitado del Generador de topologías, así como del código. 

La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL creación de reflejos para Skype Empresarial Server

SQL la creación de reflejo no se puede implementar con Skype Empresarial Server 2019. Aún se admiten otras opciones para proporcionar alta disponibilidad y recuperación ante desastres, entre las que debe elegir entre ellas. Vea [plan de alta disponibilidad y recuperación ante desastres en Skype Empresarial Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.

### <a name="in-place-upgrades"></a>Actualizaciones locales 

Las actualizaciones locales estaban disponibles en Skype Empresarial Server 2015, pero ya no son compatibles con Skype Empresarial Server 2019. Para obtener más información, consulte Migración a [Skype Empresarial Server 2019.](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

La compatibilidad con el servicio de movilidad que usan los clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Esto se anunció anteriormente en Skype Empresarial Server 2015.

Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen Mcx tendrán que actualizar a un cliente actual.

Para obtener más información, consulte [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Herramientas

Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype Empresarial Server 2019:

- Calculadora de planeamiento de capacidad de Skype Empresarial Server
- Herramientas de depuración de Skype Empresarial Server
- Herramientas del kit de recursos de Skype Empresarial Server (se quitarán algunas herramientas)
    - Call Parkometer
    - Consola de usuario de búsqueda
    - Migración de anuncios de número sin signo

Las siguientes herramientas no son compatibles con Skype Empresarial Server 2019:

- Metodología de calidad de llamadas (pero no panel de calidad de llamadas)
- Cuadro de mandos de metodología de calidad de llamadas de Microsoft, v1.5
- Herramienta de planeación de Skype Empresarial Server 2015
- Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015

### <a name="see-also"></a>Vea también

[Novedades de Skype Empresarial Server 2019](whats-new.md)

[Migrar la federación XMPP](migration/migrating-xmpp-federation.md)
