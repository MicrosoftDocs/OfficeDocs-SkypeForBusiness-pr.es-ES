---
title: Socios federados del Sistema de salas de Skype y de Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Socios federados del Sistema de salas de Skype y de Skype Empresarial

Sistema de sala de Skype se basa en el Skype unirse para el vínculo de la reunión de negocios en la convocatoria de reunión del calendario. El vínculo de unión generalmente se encuentra en el cuerpo de una convocatoria de reunión. Sin embargo, el sistema del sitio de Skype depende de este vínculo debe estar presente en las propiedades MAPI del mensaje. Cuando esta convocatoria se envía a organizaciones remotas (Skype para socios federados), de forma predeterminada sistema de sala de Skype no mostrará de la organización remoto vincular la combinación de la reunión en el calendario. De hecho, los usuarios de Outlook de la organización remoto podrá unir el Skype para reuniones de negocios con un clic derecho del calendario artículo o desde dentro el recordatorio de reunión. Debe abrir la invitación de reunión y haga clic en unirse a Skype para reuniones de negocios en el cuerpo del mensaje. 
  
El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información a la hora de enviar mensajes a través de Internet. Este método, que se conoce como Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange. Para una reunión de vínculo de unión que aparezca en un sistema remoto de sala de Skype, la organización de envío debe habilitar TNEF mediante el siguiente comando:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Una vez que TNEF está habilitado para la organización remota, los mensajes enviados a través de Internet a la organización se envían como datos adjuntos en formato TNEF. Con TNEF habilitado, cuando un Skype para la convocatoria de reunión de negocios se envía a la Skype para socio federado, sistema de sala de Skype podrá representar la unión de Skype para reuniones de negocios y los usuarios remotos puedan unirse a Skype para reuniones de negocios. 