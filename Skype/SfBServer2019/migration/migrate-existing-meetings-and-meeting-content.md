---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario pasa de un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288603"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

Cuando se mueve una cuenta de usuario a un servidor de Skype empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:
  
- **Reuniones ya programadas por el usuario**. Esto incluye mover los directorios de conferencias y los datos de la Conferencia.
    
- **Número de identificación personal (PIN) del usuario**. El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.
    
La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.
  
- **Contenido**de la reunión. Para mover el contenido compartido durante una reunión como, por ejemplo, PowerPoint, pizarra, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** . 
    

