---
title: Cambios realizados por Grant-CsSetupPermission en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Para delegar la instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa (OU) específica de Active Directory, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa unidad organizativa instalar Skype Empresarial Server en el dominio especificado sin ser miembros del grupo Administradores de dominio.
ms.openlocfilehash: 3f6de30e7068f9f44ca6d958f8ca30af866b536a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831840"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsSetupPermission en Skype Empresarial Server
 
Para delegar la instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa (OU) específica de Active Directory, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa unidad organizativa instalar Skype Empresarial Server en el dominio especificado sin ser miembros del grupo Administradores de dominio. 
  
El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la siguiente tabla:
  
**Permisos otorgados a los objetos en la unidad organizativa**

|**Los permisos se aplican a:**|**Los permisos otorgados son:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Acceso especial: <br/>  Leer servicePrincipalName <br/>  Escribir servicePrincipalName <br/>  Eliminar árbol <br/>  Cambios de directorio de replicación <br/> |
|Objetos serviceConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Leer permisos <br/>  Escribir permisos <br/>  Crear elemento secundario <br/>  Eliminar elemento secundario <br/>  Mostrar contenido <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-Server descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-WebComponents descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-MCU descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-MediationServer descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ApplicationServer descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos msRTCSIP-ConnectionPoint descendientes  <br/> | Acceso especial: <br/>  Escribir propiedad <br/>  Leer propiedad <br/>  Eliminar árbol <br/> |
|Objetos de equipo descendientes  <br/> | Acceso especial para serviceConnectionPoint: <br/>  Crear objetos secundarios <br/>  Eliminar objetos secundarios <br/>  Eliminar árbol <br/>  Acceso especial a la información pública: <br/>  Leer propiedad <br/>  Acceso especial para el nombre de host DNS: <br/>  Leer propiedad <br/> |
   

