---
title: Cambios realizados por Grant-CsSetupPermission en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Skype empresarial Server en el dominio especificado sin ser miembros del grupo administradores de dominio.
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815518"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsSetupPermission en Skype empresarial Server
 
Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Skype empresarial Server en el dominio especificado sin ser miembros del grupo administradores de dominio. 
  
El cmdlet **Grant-CsSetupPermission** concede los permisos de grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la tabla siguiente:
  
**Permisos otorgados a objetos de la OU**

|**Los permisos se aplican a:**|**Los permisos concedidos son los siguientes:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acceso especial: <br/>  Leer servicePrincipalName <br/>  Escribir servicePrincipalName <br/>  Eliminar árbol <br/>  Replicar cambios de directorio <br/> |
|Objetos serviceConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Permisos de lectura <br/>  Permisos de escritura <br/>  Crear elemento secundario <br/>  Eliminar hijo <br/>  Contenido de la lista <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-Server  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-webcomponents  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-MCU  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-MediationServer  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-ApplicationServer  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos descendientes msRTCSIP-punto de la  <br/> | Acceso especial: <br/>  Write (propiedad) <br/>  Propiedad de lectura <br/>  Eliminar árbol <br/> |
|Objetos de equipo descendientes  <br/> | Acceso especial para serviceConnectionPoint: <br/>  Crear objetos secundarios <br/>  Eliminar objetos secundarios <br/>  Eliminar árbol <br/>  Acceso especial para información pública: <br/>  Propiedad de lectura <br/>  Acceso especial para el nombre de host DNS: <br/>  Propiedad de lectura <br/> |
   

