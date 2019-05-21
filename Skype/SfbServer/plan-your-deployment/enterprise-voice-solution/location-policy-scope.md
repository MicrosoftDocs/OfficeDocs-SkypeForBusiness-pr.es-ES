---
title: Asignar ámbito de directiva de ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planear las directivas de ubicación para una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 04eb04733649e2967980e0121d17cf71221f5387
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276743"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Asignar ámbito de directiva de ubicación en Skype empresarial Server
 
Planear las directivas de ubicación para una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
  
Al igual que con otras directivas de Skype empresarial Server, las directivas de ubicación se pueden asignar en varios niveles de ámbito: global, de sitio y de usuario. Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario tiene un bit diferente al de otras directivas de Skype empresarial Server. No solo se pueden aplicar directivas de ubicación por usuario a los objetos de extremo (como usuarios y objetos de contacto de teléfono comunes), sino que también se pueden aplicar a sitios de red de Skype empresarial Server. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.
  
Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.
  
> [!NOTE]
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario. 
  

