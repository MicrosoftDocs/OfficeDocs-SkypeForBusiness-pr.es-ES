---
title: Migrar reuniones existentes y contenido de la reunión
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve de a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030374"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniones existentes y contenido de la reunión

Cuando una cuenta de usuario se mueve a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:
  
- **Las reuniones ya programadas por el usuario**. Esto incluye mover los directorios de conferencia y los datos de la conferencia.
    
- **Número de identificación personal (PIN) de un usuario**. El PIN del usuario actual sigue funcionando hasta que caduque o el usuario solicita un nuevo NIP.
    
La siguiente información de cuenta de usuario no se mueve al nuevo servidor.
  
- **Contenido de la reunión**. Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, Pizarra, datos adjuntos o datos de sondeo, use el parámetro **- MoveConferenceData** como parte del cmdlet **Move-CsUser** . 
    

