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
ms.openlocfilehash: e552f3979bf64a0fe1ebadebdf39a9a55da1e28c
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347540"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Migrar dispositivos de Lync salón del sistema (LRS) al sistema de salas de Skype v2 
Dispositivos de Lync salón del sistema (LRS) con el software del sistema de sala de Skype versión 1 (v1 SRS) llegará a fin de soporte en el 9 de octubre de 2018. Esto significa que el software de sistemas de salón de Skype no obtendrá cualquier actualizaciones de productos o revisiones después de esta fecha. Se aconseja a los clientes de dispositivos del sistema de salas de Lync mediante el sistema de salas de Skype v1 software para actualizar sus dispositivos al sistema de sala de Skype versión 2 (v2 SRS).

Software Skype salón del sistema versión 2 (v2 SRS) funciona con Microsoft Teams además de Skype para servicios de Business Server y en línea para las reuniones y llamar al método en todos los dispositivos de v2 admitidas SRS.

Los dispositivos existente **puede** seguir funcionan después de que el final del software de sistema de salas de Skype v1 admitir. Este software llegará finalmente a un error de software que necesita Microsoft para liberar una solución, o que tenga un caso donde un protocolo de comunicación existente utilizado por los cambios en el software del sistema de salas de Skype v1 o ya no se admite. Uno de estos cambios conocido es el tipo de proyectos de TLS 1.0 / 1.1 en Microsoft Office 365. Encontrará más información acerca de la [Preparación para TLS 1.0/1.1 desaprobación](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).  

## <a name="which-devices-are-affected"></a>¿Los dispositivos que se ven afectados?
Ésta es la lista de los dispositivos que se ven afectados por este cambio:
- [Sistemas inteligentes de salón](https://smartkapp.com/products/smart-room-systems)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- RL Crestron

## <a name="upgrade-options"></a>Opciones de actualización
Hay varias opciones para actualizar los sistemas de la sala de Lync a la próxima generación de sistemas de salón de Skype (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Programa de permuta de hardware de Crestron
Crestron proporcionará una actualización en el [sistema de Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de sistema de salas de Lync no Crestron. Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.  


### <a name="crestron-rl2-to-rl3"></a>Crestron RL2 a RL3
Los clientes existentes de Crestron RL2 (también denominada Crestron RL200) pueden adquirir un paquete de actualización para actualizar RL2 actual a RL3 utilizando un para un costo mínimo por dispositivo. Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.  


### <a name="smart-room-systems-upgrade--diy-program"></a>Sistemas inteligentes de salón de actualización & BRICOLAJE programa
Para los clientes inteligentes LRS, aparte de programa de permuta de hardware Crestron, Microsoft e inteligente también estén trabajando en proporcionar una solución para actualizar a v2 de sistema de salas de Skype. Microsoft también está probando una solución DIY para los clientes inteligentes LRS. Para obtener más detalles de estos programas se proporcionará en esta página de 2018 anticipado de octubre. Asegúrese de comprobar si hay actualizaciones en estas opciones de actualización.

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
