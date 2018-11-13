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
ms.openlocfilehash: a04eb857ee876b52507d21d5ee791ea327175921
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294842"
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


### <a name="crestron-rl2-to-rl3"></a>Crestron RL2 a RL3
Los clientes existentes de Crestron RL2 (también denominada Crestron RL200) pueden adquirir un paquete de actualización para actualizar RL2 actual a RL3 utilizando un para un costo mínimo por dispositivo. Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.  


### <a name="smart-room-systems-upgrade"></a>Actualización de sistemas de las salas inteligente 
Para los clientes inteligentes LRS, aparte de programa de permuta de hardware Crestron, Microsoft e inteligente también estén trabajando en proporcionar una solución para actualizar a v2 de sistema de salas de Skype. Esta actualización se proporcionará por inteligentes Technologies Inc. Consulte más información acerca de este [aquí](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>¿Qué debe hacer?
Se recomienda que planear actualizar los dispositivos de sistema de salas de Lync a sistemas de salón de Skype v2 antes de degradación de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente. Además, también puede considerar la sustitución de dispositivos existentes con nuevos dispositivos certificados para SRS v2. Para obtener detalles, consulte [dispositivos de sala](https://aka.ms/roomdevices) y también Eche un vistazo a [los requisitos de sistemas de salón de Skype v2](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Funcionalidad táctil y Pizarra no se admite todavía en el sistema de salas de Skype v2. Compatibilidad con táctil y Pizarra se encuentra en el registro de sistema de salas de Skype v2 y se agregará en CY2019 H1.

> [!NOTE]
> Software Skype salón del sistema V2 actualmente no admite protocolo TLS 1.2. Compatibilidad con TLS 1.2 es que se está trabajando en y se completará antes de degradación de TLS 1.0/1.1. Upgradging de los clientes a SRS v2 no verán ningún impacto de degradación de TLS 1.0/1.1 en los dispositivos de sala con la versión más reciente de SRS v2 app. Skype para la empresa en los clientes local debe deshabilitar TLS 1.0/1.1 hasta que admiten annouces V2 de sistema de salas de Skype para TLS 1.2. 
