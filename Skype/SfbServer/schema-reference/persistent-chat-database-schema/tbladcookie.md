---
title: tblADCookie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814760"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no NULL  <br/> |GUID de entidad de seguridad del dominio supervisado.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene un valor informativo.  <br/> |
|adcContent  <br/> |imagen (binario)  <br/> |Cookie de sincronización de Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Marca de tiempo con la hora de actualización de la fila.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Fecha/hora en que finalizará el bloqueo de la fila para efectuar cambios. Esto forma parte del mecanismo de bloqueo de software que garantiza que solo uno de los servicios de chat realice una sincronización de Active Directory por vez.  <br/> |
   
**Keys**

|**Columnas**|**Descripción**|
|:-----|:-----|
|prinGuid  <br/> |Clave principal.  <br/> |
|prinGuid  <br/> |Clave externa con búsqueda en la tabla Principal.prinGuid.  <br/> |
   

