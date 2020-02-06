---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cuando una cuenta de usuario pasa de un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813478"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando se mueve una cuenta de usuario a un servidor de Skype empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:
  
- **Reuniones ya programadas por el usuario**. Esto incluye mover los directorios de conferencias y los datos de la Conferencia.
    
- **Número de identificación personal (PIN) del usuario**. El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.
    
La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.
  
- **Contenido**de la reunión. Para mover el contenido compartido durante una reunión como, por ejemplo, PowerPoint, pizarra, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** . 
    

