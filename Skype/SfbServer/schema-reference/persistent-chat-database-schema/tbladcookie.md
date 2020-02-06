---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814708"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID principal del dominio que se está supervisando.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.  <br/> |
|adcContent  <br/> |imagen (binario)  <br/> |Cookie de sincronización de Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Marca de tiempo con la hora de actualización de la fila.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tiempo hasta que se bloquean los cambios en la fila. Esto forma parte de un mecanismo de interbloqueo de software que garantiza que solo uno de los servicios de chat realiza la sincronización de Active Directory a la vez.  <br/> |
   
**Sus**

|**Columna (s)**|**Descripción**|
|:-----|:-----|
|prinGuid  <br/> |Clave principal.  <br/> |
|prinGuid  <br/> |Clave externa con la búsqueda en la tabla principal. prinGuid.  <br/> |
   

