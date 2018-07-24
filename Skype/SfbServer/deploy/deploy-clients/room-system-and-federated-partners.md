---
title: Socios federados del Sistema de salas de Skype y de Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: 8099b5af72d4ce8e5a8be25c7fabc8563387dd46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997954"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial

Sistema de sala de Skype se basa en la Skype unirse a para el vínculo de la reunión de negocios en la convocatoria de reunión del calendario. El vínculo de unión generalmente se encuentra en el cuerpo de una convocatoria de reunión. Sin embargo, sistema de sala de Skype depende de este vínculo a estar presentes en las propiedades MAPI del mensaje. Cuando esta reunión es enviar una solicitud a las organizaciones remotas (Skype para socios federados), de forma predeterminada del sistema de salas de Skype no mostrará de la organización remoto la participación en reuniones de vínculos en el calendario. De hecho, los usuarios de Outlook en la organización remota podrán unirse a la Skype para la reunión de negocios con un clic derecho del calendario al elemento o desde dentro del aviso de reunión. Debe abrir la invitación a la reunión y haga clic en unirse a Skype para la reunión de negocios en el cuerpo del mensaje. 
  
El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información a la hora de enviar mensajes a través de Internet. Este método, que se conoce como Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange. Para una reunión de vínculo unirse a que aparezca en un sistema remoto de salón de Skype, la organización de envío debe habilitar TNEF mediante el siguiente comando:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Una vez que TNEF está habilitado para la organización remota, los mensajes enviados a través de Internet a la organización se envían como datos adjuntos en formato TNEF. Con TNEF habilitada, cuando un Skype para convocatoria de reunión de negocio se envía a la Skype para socios federados de negocio, sistema de sala de Skype podrá representar la participación de Skype para la reunión de negocios y los usuarios remotos podrán unirse a Skype para reuniones de negocios. 