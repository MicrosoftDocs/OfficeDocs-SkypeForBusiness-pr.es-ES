---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve de un servidor Skype Empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312304"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando una cuenta de usuario se mueve a un servidor Skype Empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:
  
- **Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.
    
- **Número de identificación personal (PIN) del** usuario . El PIN actual del usuario sigue funcionando hasta que expira o el usuario solicita un NUEVO PIN.
    
La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:
  
- **Contenido de reuniones**. Para mover el contenido compartido durante una reunión, como PowerPoint, pizarra, datos adjuntos o datos de sondeo, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser.** 
    

