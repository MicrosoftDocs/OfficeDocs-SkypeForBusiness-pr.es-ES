---
title: Sistema de sala de Skype y socios federados de Skype Empresarial
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información sobre cómo configurar el Sistema de sala de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820810"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Sistema de sala de Skype y socios federados de Skype Empresarial
 
Lea este tema para obtener información sobre cómo configurar el Sistema de sala de Skype para socios federados de Skype Empresarial.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Sistema de sala de Skype y socios federados de Skype Empresarial

El Sistema de salas de Skype se basa en el vínculo Unirse a una reunión de Skype Empresarial en la solicitud de reunión del calendario. El vínculo de unión suele encontrarse en el cuerpo de una solicitud de reunión. Sin embargo, el Sistema de sala de Skype depende de que este vínculo esté presente en las propiedades MAPI del mensaje. Cuando esta solicitud de reunión se envía a organizaciones remotas (socios federados de Skype Empresarial), de forma predeterminada el Sistema de salas de Skype de la organización remota no mostrará el vínculo para unirse a la reunión en el calendario. De hecho, los usuarios de Outlook de la organización remota no podrán unirse a la reunión de Skype Empresarial con un clic con el botón derecho del elemento del calendario o desde el aviso de la reunión. Deben abrir la invitación a la reunión y hacer clic en Unirse a una reunión de Skype Empresarial en el cuerpo del mensaje. 
  
El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información para enviar mensajes a través de Internet. Este método, denominado Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange. Para que un vínculo de participación en una reunión aparezca en un sistema remoto de salas de Skype, la organización de envío debe habilitar TNEF mediante el siguiente comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Después de habilitar TNEF para la organización remota, cualquier mensaje enviado a través de Internet a la organización se envía como datos adjuntos en formato TNEF. Con TNEF habilitado, cuando se envía una solicitud de reunión de Skype Empresarial al socio federado de Skype Empresarial, el Sistema de salas de Skype podrá representar la reunión de Skype Empresarial y los usuarios remotos podrán unirse a reuniones de Skype Empresarial. 
