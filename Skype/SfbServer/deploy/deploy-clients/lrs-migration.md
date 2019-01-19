---
title: Migrar dispositivos de sistema de salas de Lync al sistema de sala de Skype versión 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar el sistema de salas de Lync dispositivos para utilizar el software de sistema de salas de Skype v2.
ms.openlocfilehash: 9436c5a843f21b9913c0dbcbed6e62df8ef62ce2
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729410"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Migrar dispositivos de Lync salón del sistema (LRS) al sistema de salas de Skype v2 
Dispositivos de Lync salón del sistema (LRS) con el software del sistema de sala de Skype versión 1 (v1 SRS) ha alcanzado el [final del soporte técnico de 9 de octubre de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Esto significa que el software de sistemas de salón de Skype v1 dejarán de recibir cualquier actualizaciones de productos o revisiones ya. Se aconseja a los clientes de dispositivos del sistema de salas de Lync mediante el sistema de salas de Skype v1 software para actualizar sus dispositivos al sistema de sala de Skype versión 2 (v2 SRS).

Software Skype salón del sistema versión 2 (v2 SRS) funciona con Microsoft Teams además de Skype para servicios de Business Server y en línea para las reuniones y llamar al método en todos los dispositivos de v2 admitidas SRS.

Los dispositivos existente **puede** seguir funcionan después de que el final del software de sistema de salas de Skype v1 admitir. Sin embargo, si este software visita un error de software que necesita Microsoft para liberar una corrección, no se admite. SRS v1 usa TLS 1.0 / 1.1 que quedará obsoleto por Microsoft en el futuro. Encontrará más información acerca de la [Preparación para TLS 1.0/1.1 desaprobación](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Skype salón del sistema V2 es agregar compatibilidad para TLS 1.2 y seguirán funcionando más allá del 31 de octubre de 2018. Skype para la empresa en los clientes local debe deshabilitar TLS 1.0/1.1 hasta que admitir annouces V2 de sistema de salas de Skype para TLS 1.2 independientemente de instrucciones generales en desuso de TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>¿Los dispositivos que se ven afectados?
Ésta es la lista de los dispositivos que se ven afectados por este cambio:
- [Sistemas inteligentes de salón](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- RL Crestron

## <a name="upgrade-options"></a>Opciones de actualización
Hay varias opciones para actualizar los sistemas de la sala de Lync a la próxima generación de sistemas de salón de Skype (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Programa de permuta de hardware de Crestron
Crestron proporcionará una actualización en el [sistema de Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de sistema de salas de Lync no Crestron. Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a>Actualización de Crestron RL2 a SRS V2
Los clientes existentes de Crestron RL2 (también denominada Crestron RL200) pueden adquirir un kit de actualización para actualizar RL2 actual a RL3 utilizando un para un costo mínimo por dispositivo. Ver los detalles de este programa [aquí](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT). 


### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de las salas inteligente 
Para los clientes inteligentes LRS, aparte de programa de permuta de hardware Crestron, Microsoft e inteligente también estén trabajando en proporcionar una solución para actualizar a v2 de sistema de salas de Skype. Esta actualización se proporcionará por inteligentes Technologies Inc. Consulte más información acerca de este [aquí](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).

  
Para usar esta opción sin embargo, los clientes deben comprar además un adaptador de [Recurso compartido de pantalla Logitech](https://www.logitech.com/en-us/product/screen-share) . Microsoft proporciona instrucciones sobre cómo utilizar este adaptador con el software de sistema de salas de Skype v2. 


Busque en breve actualización instrucciones de esta página. 
  
### <a name="summary-of-upgrade-options"></a>Resumen de las opciones de actualización
En esta tabla se enumera resumen de todas las opciones disponibles para los dispositivos LRS existentes:

## <a name="what-should-you-do"></a>¿Qué debe hacer?
Se recomienda que planear actualizar los dispositivos de sistema de salas de Lync a sistemas de salón de Skype v2 antes de degradación de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente. Además, también puede considerar la sustitución de dispositivos existentes con nuevos dispositivos certificados para SRS v2. Para obtener detalles, consulte [dispositivos de sala](https://aka.ms/roomdevices) y también Eche un vistazo a [los requisitos de sistemas de salón de Skype v2](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Funcionalidad táctil y Pizarra no se admite todavía en el sistema de salas de Skype v2. Compatibilidad con táctil y Pizarra se encuentra en el registro de sistema de salas de Skype v2 y se agregará en CY2019 H1.

> [!NOTE]
> Software Skype salón del sistema V2 admite protocolo TLS 1.2 desde el 14 de diciembre de 2018 con la versión de la aplicación 4.0.64.0. Para en los clientes in situ, habilitar Threats a través de TLS 1.2 para V2 de Skype salón del sistema requiere Skype para Business Server 2015 Cummulative actualización 9 (la actualización acumulativa 9) o Skype para negocio Server 2019 Cummulative Update 1 (CU1). El cambio debe ser independiente de Skype para clientes empresariales en línea como los cambios de cliente son hacia adelante y hacia atrás compatible. 
