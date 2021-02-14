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
description: Lea este tema para obtener información sobre cómo migrar dispositivos de Lync Room System para usar el software de Salas de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662625"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de Lync Room System (LRS) a Salas de Microsoft Teams

Los dispositivos de Lync Room System (LRS) con el software Skype Room System 1 (SRS v1) finalizaron el soporte el 9 de octubre de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Es decir, el software de sistemas de la Sala de reuniones de Skype v1 ya no recibirá más actualizaciones ni correcciones. Se recomienda a los clientes que usan los dispositivos con el sistema de la Sala de reuniones de Lync con el software del sistema de Sala de reuniones de Skype v1 que actualicen sus dispositivos a las Salas de Microsoft Teams.

El software de salas de Microsoft Teams funciona con Microsoft Teams, así como con Skype Empresarial Server y con los servicios en línea para reuniones y llamadas en todos los dispositivos compatibles con salas de Microsoft Teams.

Es posible que **sus dispositivos existentes** sigan funcionando después del fin de la compatibilidad con el software de Skype Room System v1. Sin embargo, si este software encuentra un error de software que necesita que Microsoft libere una corrección, no será compatible. SRS v1 usa TLS 1.0/ 1.1, que Microsoft dejará de usar en el futuro. Puede obtener más información sobre la preparación del desuso de [TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>¿Qué dispositivos se ven afectados?

Esta es la lista de los dispositivos afectados por este cambio:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de sala INTELIGENTE](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opciones de actualización

Existen varias opciones para actualizar Sistemas de salas de Lync a la siguiente generación de salas de Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de intercambio de hardware Crestron

Crestron proporcionará una actualización al sistema [Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de Lync Room System que no son de Crestron (por ejemplo, Smart o Polycom LRS). Consulta los detalles de este [programa aquí o](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[correo electrónico](mailto:lrsupgrade@crestron.com) Compatibilidad con Lrron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Actualización de Crestron RL2 a Salas de Microsoft Teams

Los clientes existentes de Crestron RL2 (también conocido como Crestron RL200) pueden adquirir un kit de actualización para actualizar RL2 a RL3 actual usando un costo mínimo por dispositivo. Consulta aquí los detalles de este [programa.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Actualización de SMART Room Systems

Para los clientes SMART LRS, además del programa de intercambio de hardware Crestron, SMART también está trabajando en proporcionar una solución para actualizar a Microsoft Teams Rooms. SMART Technologies Inc. proporciona esta actualización al cliente en soporte técnico. Para obtener más información, haz [clic aquí.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>¿Qué debe hacer?

Le recomendamos que planee actualizar los dispositivos de Lync Room System a Microsoft Teams Rooms antes del desuso de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente. Además, también puede considerar la posibilidad de reemplazar los dispositivos existentes con nuevos dispositivos certificados para Salas de Microsoft Teams. Consulte [los dispositivos de](https://aka.ms/roomdevices) sala para obtener más información y consulte los [requisitos de salas de Microsoft Teams.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> El software de salas de Microsoft Teams admite el protocolo TLS 1.2 del 14 de diciembre de 2018 con la versión 4.0.64.0 de la aplicación. Para los clientes locales, habilitar la comunicación a través de TLS 1.2 para salas de Microsoft Teams requiere La actualización acumulativa 9 (CU9) de Skype Empresarial Server 2015 o la actualización acumulativa 1 (CU1) de Skype Empresarial Server 2019. El cambio no tiene que afectar a los clientes de Skype Empresarial Online, ya que los cambios de cliente son compatibles con versiones anteriores y 2010.
