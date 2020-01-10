---
title: Socios federados del Sistema de salas de Skype y de Skype Empresarial
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: 8ded7ba9be24cf1ac700be0ead1c7e0c3637becd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003000"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial

El sistema de salas de Skype depende del vínculo unirse a la reunión de Skype empresarial en la convocatoria de reunión del calendario. El vínculo de unión generalmente se encuentra en el cuerpo de una convocatoria de reunión. Sin embargo, el sistema de salas de Skype depende de este vínculo para estar presente en las propiedades MAPI del mensaje. Cuando se envía esta convocatoria de reunión a organizaciones remotas (socios federados de Skype empresarial), de forma predeterminada, el sistema de salas de Skype de la organización remota no mostrará el vínculo de unión a la reunión en el calendario. De hecho, todos los usuarios de Outlook de la organización remota no podrán unirse a la reunión de Skype empresarial con un clic secundario en el elemento de calendario o desde el aviso de reunión. Deben abrir la invitación a la reunión y hacer clic en unirse a la reunión de Skype empresarial en el cuerpo del mensaje. 
  
El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información a la hora de enviar mensajes a través de Internet. Este método, que se conoce como Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange. Para que un vínculo de unirse a una reunión aparezca en un sistema de salas de Skype remoto, la organización remitente debe habilitar la codificación TNEF con el siguiente comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Una vez que TNEF está habilitado para la organización remota, los mensajes enviados a través de Internet a la organización se envían como datos adjuntos en formato TNEF. Con TNEF habilitado, cuando se envía una solicitud de reunión de Skype empresarial al socio federado de Skype empresarial, el sistema de salas de Skype podrá representar la reunión de Skype empresarial y los usuarios remotos podrán unirse a reuniones de Skype empresarial. 
