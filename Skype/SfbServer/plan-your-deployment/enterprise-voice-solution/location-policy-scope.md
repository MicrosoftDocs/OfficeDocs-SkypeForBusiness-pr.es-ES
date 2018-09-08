---
title: Asignar el ámbito de directiva de ubicación en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planear las directivas de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881891"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Asignar el ámbito de directiva de ubicación en Skype para Business Server
 
Planear las directivas de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
  
Como con otro Skype para las directivas de servidor empresarial, se pueden asignar directivas de ubicación en varios niveles de ámbito: global, sitio y usuario. Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario comporta un poco diferente a con otro Skype para las directivas de servidor empresarial. No sólo se pueden aplicar las directivas de ubicación por usuario a objetos de extremo (por ejemplo, los usuarios y objetos de contacto de teléfono de área común), también se pueden aplicar a Skype Business Server sitios de red. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.
  
Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.
  
> [!NOTE]
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario. 
  

