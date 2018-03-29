---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de sincronización de protocolo ligero de acceso a directorios (LDAP) actuales.
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene las cookies de sincronización de protocolo ligero de acceso a directorios (LDAP) actuales.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no nulo  <br/> |GUID principal del dominio que se está supervisando.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nombre de dominio completo (FQDN) del controlador de dominio actual utilizado para Active Sync de servicios de directorio de dominio. Tiene valor informativo.  <br/> |
|adcContent  <br/> |imagen (binario)  <br/> |Cookie de sincronización del directorio activo.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Marca de hora con la hora de actualización de fila.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tiempo hasta que la fila está bloqueada para cambios. Esto forma parte de un mecanismo de interbloqueo de software que asegura que sólo uno de los servicios de chat no la sincronización de directorio activo a la vez.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|prinGuid  <br/> |Clave principal.  <br/> |
|prinGuid  <br/> |Clave externa con la búsqueda en la tabla Principal.prinGuid.  <br/> |
   

