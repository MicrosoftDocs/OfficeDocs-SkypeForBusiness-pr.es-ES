---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de protocolo ligero de acceso a directorios (LDAP) actuales.
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929948"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene las cookies de protocolo ligero de acceso a directorios (LDAP) actuales.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no es nulo  <br/> |Entidad de seguridad de GUID del dominio que se está supervisando.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.  <br/> |
|adcContent  <br/> |imagen (binario)  <br/> |Cookie de sincronización del directorio activo.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Marca de tiempo con la hora de actualización de fila.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tiempo hasta que la fila está bloqueada para que los cambios. Esto es parte de un mecanismo de interbloqueo de software que se asegura de que sólo uno de los servicios de chat no la sincronización de Active Directory a la vez.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|prinGuid  <br/> |Clave principal.  <br/> |
|prinGuid  <br/> |Clave externa con búsqueda en la tabla Principal.prinGuid.  <br/> |
   

