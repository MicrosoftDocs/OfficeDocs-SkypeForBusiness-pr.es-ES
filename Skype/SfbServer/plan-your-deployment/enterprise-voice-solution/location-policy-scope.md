---
title: Asignar ámbito de directiva de ubicación en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planeación de directivas de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
---

# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Asignar ámbito de directiva de ubicación en Skype Empresarial Server
 
Planeación de directivas de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
  
Al igual que con otras Skype Empresarial Server, las directivas de ubicación se pueden asignar en varios niveles de ámbito: global, de sitio y de usuario. Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario se comporta de forma un poco diferente que con otras directivas Skype Empresarial Server usuario. No solo se pueden aplicar directivas de ubicación por usuario a objetos de punto de conexión (como usuarios y objetos de contacto Teléfono área común), sino que también se pueden aplicar Skype Empresarial Server sitios de red. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación en el nivel de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en sitio de la red sustituye a cualquier otra configuración de directiva de usuario.
  
Cada sitio de red tiene asignada una directiva de ubicación, y cada directiva tendrá asignados valores diferentes de Uso de RTC, URI de notificación y URI de conferencia.
  
> [!NOTE]
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de usuarios de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red independientemente de a qué grupo de usuarios o sitio esté asignado el usuario. 
  

