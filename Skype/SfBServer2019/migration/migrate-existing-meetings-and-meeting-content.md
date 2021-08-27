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
ms.localizationpriority: medium
description: 'Cuando una cuenta de usuario se mueve de un servidor Skype Empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 826b511250e46e2c87720a5b074b43cd545b15c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589306"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando una cuenta de usuario se mueve a un servidor Skype Empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:
  
- **Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.
    
- **Número de identificación personal (PIN) del** usuario . El PIN actual del usuario sigue funcionando hasta que expira o el usuario solicita un NUEVO PIN.
    
La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:
  
- **Contenido de reuniones**. Para mover el contenido compartido durante una reunión, como PowerPoint, pizarra, datos adjuntos o datos de sondeo, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser.** 
    

