---
title: Cambios realizados por Grant-CsSetupPermission en Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar el programa de instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa específica de Active Directory (OU), lo que permite a los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa para instalar Skype para Business Server en el dominio especificado sin ser miembros del grupo de administradores de dominio.
ms.openlocfilehash: 3976cb22a947e9a9590989895cf688465c8f5ef0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213392"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsSetupPermission en Skype para Business Server
 
Para delegar el programa de instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa específica de Active Directory (OU), lo que permite a los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa para instalar Skype para Business Server en el dominio especificado sin ser miembros del grupo de administradores de dominio. 
  
El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, tal como se especifica en la siguiente tabla:
  
**Permisos otorgados a los objetos en la unidad organizativa**

|**Los permisos se aplican a:**|**Los permisos otorgados son:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acceso especial: <br/>  Leer servicePrincipalName <br/>  Escribir servicePrincipalName <br/>  Eliminar árbol <br/>  Replicar cambios de directorio <br/> |
|Objetos serviceConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Permisos de lectura <br/>  Permisos de escritura <br/>  Crear secundario <br/>  Eliminar secundario <br/>  Contenido de lista <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-Server descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-WebComponents descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-MCU descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-MediationServer descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ApplicationServer descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Escribir (propiedad) <br/>  Lectura (propiedad) <br/>  Eliminar árbol <br/> |
|Objetos de equipo descendientes  <br/> | Acceso especial para serviceConnectionPoint: <br/>  Crear objetos secundarios <br/>  Eliminar objetos secundarios <br/>  Eliminar árbol <br/>  Acceso especial información pública: <br/>  Lectura (propiedad) <br/>  Acceso especial para el nombre de host DNS: <br/>  Lectura (propiedad) <br/> |
   

