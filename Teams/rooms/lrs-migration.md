---
title: Migrar dispositivos del sistema de salas de Lync a salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar dispositivos de Lync Room System para usar el software Salas de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117528"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de Lync Room System (LRS) a salas de Microsoft Teams

Los dispositivos de Lync Room System (LRS) con el software sistema de sala de Skype 1 (SRS v1) han alcanzado el fin del soporte técnico el 9 de octubre de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Es decir, el software de sistemas de la Sala de reuniones de Skype v1 ya no recibirá más actualizaciones ni correcciones. Se recomienda a los clientes que usan los dispositivos con el sistema de la Sala de reuniones de Lync con el software del sistema de Sala de reuniones de Skype v1 que actualicen sus dispositivos a las Salas de Microsoft Teams.

El software Salas de Microsoft Teams funciona con Microsoft Teams, además de servicios de Skype Empresarial Server y en línea para reuniones y llamadas en todos los dispositivos compatibles con Salas de Microsoft Teams.

Es posible que los **dispositivos existentes** sigan funcionando después del fin de la compatibilidad con el software de Skype Room System v1. Sin embargo, si este software encuentra un error de software que necesita que Microsoft suelte una corrección, no será compatible. SRS v1 usa TLS 1.0/ 1.1 que Microsoft dejará de usar en el futuro. Puede obtener más información sobre [cómo preparar la desusación de TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>¿Qué dispositivos se ven afectados?

Esta es la lista de los dispositivos que se ven afectados por este cambio:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de sala SMART](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opciones de actualización

Hay varias opciones para actualizar los sistemas de salas de Lync a la siguiente generación de salas de Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de intercambio de hardware Crestron

Crestron proporcionará una actualización al sistema [Sr. Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente para todos los clientes del Sistema de sala de Lync que no son Crestron (por ejemplo, Smart o Polycom LRS). Vea los detalles de este programa [aquí o](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[correo electrónico](mailto:lrsupgrade@crestron.com) Soporte de Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Actualización de Crestron RL2 a salas de Microsoft Teams

Los clientes existentes de Crestron RL2 (también conocido como Crestron RL200) pueden adquirir un kit de actualización para actualizar el RL2 actual a RL3 con un costo mínimo por dispositivo. Vea los detalles de este [programa aquí.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de sala SMART

Para los clientes de SMART LRS, además del programa de intercambio de hardware Crestron, SMART también está trabajando en proporcionar una solución para actualizar a salas de Microsoft Teams. SMART Technologies Inc. le proporciona esta actualización al cliente en el soporte técnico del producto. Vea más información sobre esto [aquí.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>¿Qué debería hacer?

Le recomendamos que planee actualizar los dispositivos del sistema de salas de Lync a salas de Microsoft Teams antes de que TLS 1.0/1.1 desaprotese con las opciones de actualización mencionadas anteriormente. Además, también puede considerar la posibilidad de reemplazar dispositivos existentes con nuevos dispositivos certificados para Salas de Microsoft Teams. Vea [Dispositivos de sala](https://aka.ms/roomdevices) para obtener más información y también vea los requisitos de salas de Microsoft [Teams.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> El software Salas de Microsoft Teams admite el protocolo TLS 1.2 a partir del 14 de diciembre de 2018 con la versión 4.0.64.0 de la aplicación. Para los clientes locales, para habilitar la comunicación a través de TLS 1.2 para salas de Microsoft Teams se requiere la actualización acumulativa 9 (CU9) de Skype Empresarial Server 2015 o la actualización acumulativa 1 (CU1) de Skype Empresarial Server 2019. El cambio no debe afectar a los clientes de Skype Empresarial Online, ya que los cambios de cliente son compatibles con el avance y el retroceso.