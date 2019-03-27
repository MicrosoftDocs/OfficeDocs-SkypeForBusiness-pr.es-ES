---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve de a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874664"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando una cuenta de usuario se mueve a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:
  
- **Las reuniones ya programadas por el usuario**. Esto incluye mover los directorios de conferencia y los datos de la conferencia.
    
- **Número de identificación personal (PIN) de un usuario**. El PIN del usuario actual sigue funcionando hasta que caduque o el usuario solicita un nuevo NIP.
    
La siguiente información de cuenta de usuario no se mueve al nuevo servidor.
  
- **Contenido de la reunión**. Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, Pizarra, datos adjuntos o datos de sondeo, use el parámetro **- MoveConferenceData** como parte del cmdlet **Move-CsUser** . 
    

