---
title: Skype Sistema de sala y Skype Empresarial asociados federados
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información sobre cómo configurar Skype room system para Skype Empresarial asociados federados.
ms.openlocfilehash: ee9d7013df141cfe937f1c006a5e659a9e8a7478
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841942"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema de sala y Skype Empresarial asociados federados
 
Lea este tema para obtener información sobre cómo configurar Skype room system para Skype Empresarial asociados federados.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema de sala y Skype Empresarial asociados federados

Skype El sistema de salas se basa en el vínculo Unirse Skype Empresarial reunión en la solicitud de reunión del calendario. El vínculo de unión suele encontrarse en el cuerpo de una solicitud de reunión. Sin embargo, Skype room system depende de que este vínculo esté presente en las propiedades MAPI del mensaje. Cuando esta solicitud de reunión se envía Skype Empresarial organizaciones remotas (asociados federados), de forma predeterminada, el sistema de salas de Skype de la organización remota no mostrará el vínculo de unión a la reunión en el calendario. De hecho, los Outlook usuarios de la organización remota no podrán unirse a la reunión de Skype Empresarial con un clic con el botón derecho del elemento del calendario o desde dentro del aviso de la reunión. Deben abrir la invitación a la reunión y hacer clic en Unirse Skype Empresarial reunión en el cuerpo del mensaje. 
  
La razón de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información para enviar mensajes a través de Internet. Este método, denominado Transport Neutral Encapsulation Format (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una Exchange organización. Para que un vínculo de unión a una reunión aparezca en un sistema de salas Skype remoto, la organización de envío debe habilitar TNEF mediante el siguiente comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Después de habilitar TNEF para la organización remota, cualquier mensaje enviado a través de Internet a la organización se envía como datos adjuntos en formato TNEF. Con TNEF habilitado, cuando se envía una solicitud de reunión de Skype Empresarial al asociado federado de Skype Empresarial, el sistema de salas de Skype podrá representar la reunión unirse Skype Empresarial y los usuarios remotos podrán unirse Skype Empresarial reuniones. 
