---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: la tabla tblPrincipal contiene a todas las entidades, incluidos los usuarios, carpetas y grupos.
ms.openlocfilehash: 2c1b25cce9183a68a276dee6167052cdd068eecf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929885"
---
# <a name="tblprincipal"></a>tblPrincipal
 
la tabla tblPrincipal contiene a todas las entidades, incluidos los usuarios, carpetas y grupos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|prinGuid  <br/> |GUID, no es nulo  <br/> |GUID de la entidad de seguridad. A grandes rasgos se usa como una clave principal alternativa porque su significado se cruza en el espacio de los servicios de dominio de Active Directory. (El GUID de una entidad de seguridad almacenado en caché es igual que el GUID del objeto de Active Directory correspondiente.)  <br/> |
|prinUri  <br/> |nvarchar (256), no es nulo  <br/> |URI de la entidad de seguridad. La combinación de SIP se utiliza para los usuarios y ma-agrupados se utilizan para casi todo lo demás.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nombre común. Se usa sólo por tipos de usuario.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nombre para mostrar. Se usa sólo por tipos de usuario.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nombre de la compañía. Se usa sólo por tipos de usuario.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Correo electrónico. Se usa sólo por tipos de usuario.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nombre de dominio de la que la entidad de seguridad es una versión en caché de objeto de Active Directory. Puede ser Null para los tipos que no son objetos de Active Directory (por ejemplo, los usuarios del sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nombre principal de usuario del usuario (UPN). Se usa sólo por tipos de usuario normal.  <br/> |
|prinDisabled  <br/> |smallint, no es nulo  <br/> | 0: entidad de seguridad está activa. <br/>  1: entidad de seguridad está deshabilitada porque están deshabilitadas las funciones SIP del usuario. <br/>  2: se elimina la entidad de seguridad porque se ha eliminado el objeto de AD asociado. <br/> |
|prinTypeID  <br/> |smallint, no es nulo  <br/> |Tipo de entidad de seguridad (de la tabla tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype para asignación de grupo de servidores de cliente empresarial para la entidad de seguridad.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Persistent Chat Server valor de directiva de usuario, si la directiva de tipo de etiqueta está presente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |Identificador de entidad del creador.  <br/> |
|prinAddedOn  <br/> |bigint, no es nulo  <br/> |Marca de tiempo para la hora de creación.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |Identificador de la entidad de seguridad que actualizó por última vez esto.  <br/> |
|prinUpdatedOn  <br/> |bigint, no es nulo  <br/> |Marca de tiempo para la última actualización.  <br/> |
|prinVerifiedOn  <br/> |DateTime, no es nulo  <br/> |Actualización de fecha y hora de la última sincronización de Active Directory para la entidad de seguridad.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinTypeID  <br/> |Clave externa con búsqueda en la tabla tblPrincipalType.ptypeID.  <br/> |
   

