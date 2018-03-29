---
title: Cambios realizados por Grant CsSetupPermission en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar la instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa específica de Active Directory (OU), lo que permite a los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa para instalar Skype para Business Server en el dominio especificado sin ser miembros del grupo Administradores de dominio.
ms.openlocfilehash: 6c87ad11e0c125f2a58f2518218060b2a3636f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Cambios realizados por Grant CsSetupPermission en Skype para Business Server
 
Para delegar la instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa específica de Active Directory (OU), lo que permite a los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa para instalar Skype para Business Server en el dominio especificado sin ser miembros del grupo Administradores de dominio. 
  
El cmdlet **Grant CsSetupPermission** concede los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la tabla siguiente:
  
**Permisos que se conceden a objetos en la unidad organizativa**

|**Los permisos se aplican a:**|**Permisos concedidos son:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acceso especial: <br/>  Leer nombrePrincipalDeServicio <br/>  Escribir nombrePrincipalDeServicio <br/>  Eliminar árbol <br/>  Replicar cambios de directorio <br/> |
|Objetos descendientes serviceConnectionPoint  <br/> | Acceso especial: <br/>  Permisos de lectura <br/>  Permisos de escritura <br/>  Crear secundarios <br/>  Eliminar secundario <br/>  Mostrar el contenido <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-Server descendientes  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-WebComponents descendientes  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-MCU  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-MediationServer  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ApplicationServer descendientes  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Propiedad de escritura <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes de equipo  <br/> | Acceso especial para serviceConnectionPoint: <br/>  Crear objetos secundarios <br/>  Eliminar objetos secundarios <br/>  Eliminar árbol <br/>  Acceso a información pública: <br/>  Propiedad de lectura <br/>  Acceso especial para el nombre de host DNS: <br/>  Propiedad de lectura <br/> |
   

