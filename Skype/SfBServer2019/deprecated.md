---
title: ¿Qué está en desuso de Skype para Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Estas características se han quitado de Skype para Business Server 2019.'
ms.openlocfilehash: 66366c2272db8d6f605fde6dc066f730543883b6
ms.sourcegitcommit: 27cd6d540485d5a1557a6131612894ca2f3516ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025083"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>¿Qué está en desuso de Skype para Business Server 2019 

Obtenga información sobre las características y funciones que están en desuso en Skype para Business Server 2019. Para obtener información acerca de las nuevas características de Skype para Business Server 2019, consulte [Novedades en Skype para Business Server 2019](whats-new.md).

Algunas características desaprovisionamiento emphasised se incluyen en Skype para Business Server 2019 para la compatibilidad con versiones anteriores del producto. 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Características desusadas en Skype para Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Puertas de enlace XMPP de Skype para Business Server

Skype para Business Server 2015 y sus predecesoras permite configurar un proxy de mensajería Extensible y protocolo de presencia (XMPP) en el servidor perimetral y una puerta de enlace de XMPP en el grupo de servidores Front-End o de servidor Front-End. Esta funcionalidad ya no está disponible en Skype para Business Server 2019.


### <a name="persistent-chat-for-skype-for-business-server"></a>Persistent Chat de Skype para Business Server

Persistent Chat Server es un rol opcional que permite a varios usuarios de la organización participar en conversaciones de salón de chat que persisten a lo largo del tiempo. Chat en grupo no se puede implementar con Skype para Business Server 2019. Esta función de servidor se ha quitado el generador de topología, así como desde el código. 

La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).   

### <a name="sql-mirroring-for-skype-for-business-server"></a>Creación de reflejos SQL para Skype para Business Server

La creación de reflejos de SQL no se puede implementar con Skype para Business Server 2019. Aún se admiten otras opciones para proporcionar alta disponibilidad y recuperación ante desastres y debe elegir entre ellos. Consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.

### <a name="in-place-upgrades"></a>Actualizaciones en contexto 

Las actualizaciones en contexto estaban disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. En paralelo se admite la actualización y coexistencia, consulte [migración de Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.

###  <a name="mobility-service-mcx"></a>Servicio de movilidad (Mcx)

Compatibilidad con el servicio movilidad usado por los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Anteriormente se presentó en Skype para Business Server 2015.

Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con Mcx necesitará actualizar a un cliente actual.

Para obtener más detalles, vea [planear para movilidad de Skype para Business Server](../SfbServer/plan-your-deployment/mobility.md) y la [comparación de características de cliente móvil de Skype para la empresa](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Herramientas

Las siguientes herramientas no estará disponibles para su uso en la versión inicial de Skype para Business Server 2019:

- Skype para Calculadora de planeación de la capacidad de servidor empresarial
- Skype para herramientas de depuración de Business Server
- Skype para (algunas herramientas se quitará) de herramientas del Kit de recursos de servidor empresarial
    - Call Parkometer (Estacionamiento de llamadas)
    - Consola de usuario de búsqueda
    - Migración de anuncio de número sin asignar

Las siguientes herramientas no son compatibles con Skype para Business Server 2019:

- Metodología de calidad de llamadas (pero no llamar al panel de calidad)
- Cuadro de mandos de metodología de calidad de llamada de Microsoft, v1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Vea también

[¿Qué es una novedad de Skype para Business Server 2019](whats-new.md)

[Migración de la federación XMPP](migration/migrating-xmpp-federation.md)