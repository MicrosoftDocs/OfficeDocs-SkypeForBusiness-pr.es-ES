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
description: 'Cuando se mueve una cuenta de usuario desde un servidor de Skype Empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752692"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando se mueve una cuenta de usuario a un servidor de Skype Empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:
  
- **Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.
    
- **Número de identificación personal (PIN) del usuario.** El PIN actual del usuario sigue funcionando hasta que expira o el usuario solicita un NUEVO PIN.
    
La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:
  
- **Contenido de reuniones**. Para mover el contenido compartido durante una reunión, como PowerPoint, pizarra, datos adjuntos o datos de sondeo, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser.** 
    

