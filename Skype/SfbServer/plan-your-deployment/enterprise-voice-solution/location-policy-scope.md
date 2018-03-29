---
title: Asignar ámbito de directiva de ubicación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planificación de las políticas de ubicación para una implementación de E9-1-1 en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 472ca2e6382a92005476eb7ed7c6bcfb22e71f85
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="assign-location-policy-scope-in-skype-for-business-server-2015"></a>Asignar ámbito de directiva de ubicación en Skype Empresarial Server 2015
 
Planificación de las políticas de ubicación para una implementación de E9-1-1 en Skype para Business Server Telefonía IP empresarial.
  
Como con otro Skype para directivas de Business Server, se pueden asignar políticas de ubicación en varios niveles de ámbito: global, sitios y usuarios. Sin embargo, el ámbito de las políticas de ubicación de nivel de usuario comporta un poco distinta con otro Skype para las directivas de servidor empresarial. No sólo se pueden aplicar las políticas de ubicación de cada usuario a los objetos de extremo (por ejemplo, los usuarios y objetos de contacto teléfono de área común), pueden aplicarse también a Skype para sitios de red de servidor empresarial. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.
  
Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.
  
> [!NOTE]
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario. 
  

