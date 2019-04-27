---
title: Migrar dispositivos de sistema de salas de Lync a las salas de los equipos de Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar el sistema de salas de Lync dispositivos para utilizar el software de salas de equipos de Microsoft.
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363001"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de Lync salón del sistema (LRS) a las salas de los equipos de Microsoft

Dispositivos de Lync salón del sistema (LRS) con el software del sistema de sala de Skype versión 1 (v1 SRS) ha alcanzado el [final del soporte técnico de 9 de octubre de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Esto significa que el software de sistemas de salón de Skype v1 dejarán de recibir cualquier actualizaciones de productos o revisiones ya. Se aconseja a los clientes de dispositivos del sistema de salas de Lync mediante el sistema de salas de Skype v1 software para actualizar sus dispositivos a salones de los equipos de Microsoft.

Salones de los equipos de Microsoft software funciona con Microsoft Teams además de Skype para servicios de Business Server y en línea para las reuniones y llamadas en todos los salones de los equipos de Microsoft de dispositivos admitidos.

Los dispositivos existente **puede** seguir funcionan después de que el final del software de sistema de salas de Skype v1 admitir. Sin embargo, si este software visita un error de software que necesita Microsoft para liberar una corrección, no se admite. SRS v1 usa TLS 1.0 / 1.1 que quedará obsoleto por Microsoft en el futuro. Encontrará más información acerca de la [Preparación para TLS 1.0/1.1 desaprobación](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Salones de los equipos de Microsoft es agregar compatibilidad para TLS 1.2 y seguirán funcionando más allá del 31 de octubre de 2018. Skype para la empresa local de clientes deben deshabilitar TLS 1.0/1.1 hasta que salones de los equipos de Microsoft anuncia soporte para TLS 1.2 independientemente de instrucciones generales en desuso de TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>¿Los dispositivos que se ven afectados?

Ésta es la lista de los dispositivos que se ven afectados por este cambio:

- RL Crestron
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas inteligentes de salón](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opciones de actualización

Hay varias opciones para actualizar los sistemas de la sala de Lync a la siguiente generación de salones de los equipos de Microsoft.

### <a name="crestron-hardware-trade-in-program"></a>Programa de permuta de hardware de Crestron

Crestron proporcionará una actualización en el [sistema de Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de sistema de salas de Lync no Crestron (por ejemplo inteligente o Polycom LRS). Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, -->[correo electrónico](mailto:lrsupgrade@crestron.com) Compatibilidad con Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Actualización de Crestron RL2 a las salas de los equipos de Microsoft

Los clientes existentes de Crestron RL2 (también denominada Crestron RL200) pueden adquirir un kit de actualización para actualizar RL2 actual a RL3 utilizando un para un costo mínimo por dispositivo. Ver los detalles de este programa [aquí](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de las salas inteligente

Para los clientes inteligentes LRS, aparte de programa de permuta de hardware Crestron, inteligente también está trabajando en proporcionar una solución para actualizar a salones de los equipos de Microsoft. Esta actualización se proporcionará inteligentes Inc. de tecnologías de cliente en el servicio de soporte técnico. Consulte más información acerca de este [aquí](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>¿Qué debe hacer?

Se recomienda que planear actualizar los dispositivos de sistema de salas de Lync a las salas de los equipos de Microsoft antes de degradación de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente. Además, también puede considerar la sustitución de dispositivos existentes con nuevos dispositivos certificados para salas de equipos de Microsoft. Para obtener detalles, consulte [dispositivos de sala](https://aka.ms/roomdevices) y también Eche un vistazo a [los requisitos de salas de equipos de Microsoft](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Funcionalidad táctil y Pizarra no se admite todavía en salas de equipos de Microsoft. Compatibilidad con táctil y Pizarra actualmente está prevista para salas de equipos de Microsoft y se agregará en 2019.

> [!NOTE]
> Software de salas de equipos de Microsoft es compatible con el protocolo TLS 1.2 a partir de 14 de diciembre de 2018 con la versión de la aplicación 4.0.64.0. Para los clientes locales, habilitar la comunicación a través de TLS 1.2 para salas de equipos de Microsoft requiere Skype para Business Server 2015 actualización acumulativa 9 (la actualización acumulativa 9) o Skype para Business Server 2019 acumulativa Update 1 (CU1). El cambio no debería afectar a Skype para clientes empresariales en línea que los cambios del cliente hacia delante y hacia atrás compatible.
