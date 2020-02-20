---
title: Qué está en desuso en Skype empresarial Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han quitado de Skype empresarial Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125223"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Qué está en desuso en Skype empresarial Server 2019

Obtenga información sobre las características y funciones que están en desuso en Skype empresarial Server 2019. Para obtener información acerca de las nuevas características de Skype empresarial Server 2019, consulte [what's in Skype for Business server 2019](whats-new.md).

Algunas características que se pueden recalcar se incluyen en Skype empresarial Server 2019 por compatibilidad con versiones anteriores del producto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Características en desuso en Skype empresarial Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Puertas de enlace XMPP para Skype empresarial Server

Skype empresarial Server 2015 y sus antecesores le permiten configurar un proxy de protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end. Esta funcionalidad ya no está disponible en Skype empresarial Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente de Skype empresarial Server

El servidor de chat persistente es un rol opcional que permite que varios usuarios de la organización participen en las conversaciones del salón de chat que persisten a lo largo del tiempo. Chat persistente no se puede implementar con Skype empresarial Server 2019. Este rol de servidor se quita del generador de topologías, así como del código. 

La misma funcionalidad está disponible en Microsoft Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Creación de reflejos de SQL para Skype empresarial Server

La creación de reflejos de SQL no se puede implementar con Skype empresarial Server 2019. También se admiten otras opciones para la alta disponibilidad y la recuperación ante desastres y debe elegir entre ellas. Consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.

### <a name="in-place-upgrades"></a>Actualizaciones en el lugar 

Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Se admite la coexistencia y la actualización en paralelo, consulte [migración a Skype empresarial Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.

### <a name="mobility-service-mcx"></a>Servicio de movilidad (MCX)

El soporte del servicio de movilidad usado por los clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Esto se anunció anteriormente en Skype empresarial Server 2015.

Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.

Para obtener más información, consulte [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile Client Feature Comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Herramientas

Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype empresarial Server 2019:

- Calculadora de planeación de capacidad de Skype empresarial Server
- Herramientas de depuración de Skype empresarial Server
- Herramientas del kit de recursos de Skype empresarial Server (se quitan algunas herramientas)
    - Llamar a Parkometer
    - Consola del usuario de búsqueda
    - Migración del anuncio de número sin asignar

Las siguientes herramientas no son compatibles con Skype empresarial Server 2019:

- Metodología de calidad de llamadas (pero no panel de calidad de llamadas)
- Cuadro de mandos de metodología de calidad de llamadas de Microsoft, v 1.5
- Herramienta de planeación de Skype empresarial Server 2015
- Herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015

### <a name="see-also"></a>Vea también

[Novedades de Skype empresarial Server 2019](whats-new.md)

[Migración de la Federación XMPP](migration/migrating-xmpp-federation.md)
