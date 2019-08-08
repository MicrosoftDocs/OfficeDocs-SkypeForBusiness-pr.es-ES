---
title: Migrar dispositivos de sistema de salas de Lync a salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar dispositivos de sistema de salas de Lync para usar el software de salas de Microsoft Teams.
ms.openlocfilehash: d07f214707253dc91495da1d219ed84dab2eec5d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243371"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de Lync Room System (LRS) a salas de Microsoft Teams

Los dispositivos de Lync Room System (LRS) con el software de sistema de salas de Skype versión 1 (SRS V1) han alcanzado el [fin de asistencia del 9 de octubre de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Esto significa que el software de los sistemas de la sala de Skype v1 ya no recibirá más actualizaciones de productos ni correcciones. Se recomienda que los clientes con dispositivos de sistema de sala de Lync con el software sistema de salas de Skype v1 actualicen sus dispositivos a las salas de Microsoft Teams.

El software Microsoft Teams Rooms funciona con Microsoft Teams además de Skype empresarial Server y los servicios en línea para reuniones y llamadas en todos los dispositivos compatibles con Microsoft Teams.

Los dispositivos existentes **pueden** continuar funcionando después de que finalice el soporte técnico del software de Skype Room System V1. Sin embargo, si este software llega a un error de software que necesita que Microsoft publique una corrección, no será compatible. SRS v1 usa TLS 1.0/1,1, que Microsoft detendrá en el futuro. Puede obtener más información sobre cómo [prepararse para el desuso de TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Salas de Microsoft Teams agrega soporte técnico para TLS 1,2 y seguirá funcionando después del 31 de octubre de 2018. Los clientes locales de Skype empresarial no deben deshabilitar TLS 1.0/1.1 hasta que las salas de Microsoft Teams anuncien el soporte para TLS 1,2, independientemente de las pautas generales de la degradación de TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>¿Qué dispositivos se ven afectados?

Esta es la lista de los dispositivos afectados por este cambio:

- RL Crestron
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de salas inteligentes](https://support.smarttech.com/en/hardware/room-systems-skype)
- [CX8000 Polycom](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opciones de actualización

Hay varias opciones para actualizar sistemas de salas de Lync a la nueva generación de salas de Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de intercambio de hardware de Crestron

Crestron proporcionará una actualización del [sistema de Crestron Sr](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente para todos los clientes del sistema de la sala de Lync que no sean Crestron (por ejemplo, inteligente o Polycom LRS). Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, -->[correo electrónico](mailto:lrsupgrade@crestron.com) Compatibilidad con el Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 actualización a salas de Microsoft Teams

Los clientes de Crestron RL2 (también conocidos como Crestron RL200) pueden adquirir un kit de actualización para actualizar RL2 actuales a RL3 con un precio mínimo por dispositivo. Ver los detalles de este programa [aquí](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de salas inteligentes

Para los clientes de LRS inteligente, además de un programa de permuta de hardware para Crestron, SMART también está trabajando en proporcionar una solución para actualizar a salas de Microsoft Teams. SMART Technologies Inc. esta actualización será proporcionada por el cliente con soporte técnico. Para obtener más información, consulta [aquí](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>¿Qué debe hacer?

Le recomendamos que planee la actualización de los dispositivos de sistema de la sala de Lync a salas de Microsoft Teams antes de la degradación de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente. Además, también puede considerar la posibilidad de reemplazar los dispositivos existentes con nuevos dispositivos certificados para salas de Microsoft Teams. Para obtener más información, consulte dispositivos de la [sala](https://aka.ms/roomdevices) y eche un vistazo a [los requisitos de las salas de Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Las salas de la pizarra y la función táctil aún no son compatibles con las salas de Microsoft Teams. La asistencia táctil y de pizarra está actualmente planificada para salas de Microsoft Teams y se agregará en 2019.

> [!NOTE]
> El software salas de Microsoft Teams es compatible con el protocolo TLS 1,2 a partir del 14 de diciembre de 2018 con la versión de la aplicación 4.0.64.0. En el caso de los clientes locales, la habilitación de la comunicación a través de TLS 1,2 para salas de Microsoft Teams requiere la actualización acumulativa 9 (CU9) de Skype empresarial 2015 o la actualización acumulativa 1 de Skype empresarial 2019 (CU1). El cambio no debe afectar a los clientes de Skype empresarial online debido a que los cambios de cliente son reenviados y compatibles con versiones anteriores.
