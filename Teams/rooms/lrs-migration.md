---
title: Migrar dispositivos de Lync Room System a Salas de Microsoft Teams
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
description: Lea este tema para obtener información sobre cómo migrar dispositivos de Lync Room System para usar Salas de Microsoft Teams software.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a700e66a966035b52a3036210e39c09612ed18b5df34430545987c51c40575f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301076"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de Lync Room System (LRS) a Salas de Microsoft Teams

Los dispositivos de Lync Room System (LRS) con software Skype Room System versión 1 (SRS v1) han alcanzado el fin del soporte técnico el 9 de octubre de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Es decir, el software de sistemas de la Sala de reuniones de Skype v1 ya no recibirá más actualizaciones ni correcciones. Se recomienda a los clientes que usan los dispositivos con el sistema de la Sala de reuniones de Lync con el software del sistema de Sala de reuniones de Skype v1 que actualicen sus dispositivos a las Salas de Microsoft Teams.

Salas de Microsoft Teams software funciona con Microsoft Teams además de servicios Skype Empresarial Server y en línea para reuniones y llamadas en todos los Salas de Microsoft Teams dispositivos compatibles.

Es posible que **los** dispositivos existentes sigan funcionando después del Skype de software de Room System v1. Sin embargo, si este software encuentra un error de software que necesita que Microsoft suelte una corrección, no será compatible. SRS v1 usa TLS 1.0/ 1.1 que Microsoft dejará de usar en el futuro. Puede obtener más información sobre [cómo preparar la desusación de TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>¿Qué dispositivos se ven afectados?

Esta es la lista de los dispositivos que se ven afectados por este cambio:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de sala SMART](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opciones de actualización

Hay varias opciones para actualizar los sistemas de salón de Lync a la siguiente generación de Salas de Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de intercambio de hardware Crestron

Crestron proporcionará una actualización al sistema [Sr. Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente para todos los clientes del Sistema de sala de Lync que no son Crestron (por ejemplo, Smart o Polycom LRS). Vea los detalles de este programa [aquí o](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[correo electrónico](mailto:lrsupgrade@crestron.com) Soporte de Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Upgrade de Crestron RL2 a Salas de Microsoft Teams

Los clientes existentes de Crestron RL2 (también conocido como Crestron RL200) pueden adquirir un kit de actualización para actualizar el RL2 actual a RL3 con un costo mínimo por dispositivo. Vea los detalles de este [programa aquí.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de sala SMART

Para los clientes de SMART LRS, además del programa de intercambio de hardware Crestron, SMART también está trabajando en proporcionar una solución para actualizar a Salas de Microsoft Teams. SMART Technologies Inc. le proporciona esta actualización al cliente en el soporte técnico del producto. Vea más información sobre esto [aquí.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>¿Qué debería hacer?

Le recomendamos que planee actualizar los dispositivos de Lync Room System para que Salas de Microsoft Teams antes de que TLS 1.0/1.1 desaprobase con las opciones de actualización mencionadas anteriormente. Además, también puede considerar la posibilidad de reemplazar dispositivos existentes por nuevos dispositivos certificados para Salas de Microsoft Teams. Vea [Dispositivos de sala](https://aka.ms/roomdevices) para obtener más información y también echar un vistazo a Salas de Microsoft Teams [requisitos.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Salas de Microsoft Teams software admite el protocolo TLS 1.2 a partir del 14 de diciembre de 2018 con la versión 4.0.64.0 de la aplicación. Para los clientes locales, habilitar la comunicación a través de TLS 1.2 para Salas de Microsoft Teams requiere Skype Empresarial Server actualización acumulativa de 2015 9 (CU9) o Skype Empresarial Server 2019 actualización acumulativa 1 (CU1). El cambio no debe afectar Skype Empresarial clientes en línea, ya que los cambios de cliente son compatibles con el avance y el retroceso.