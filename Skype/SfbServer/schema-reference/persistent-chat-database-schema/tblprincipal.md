---
title: tblPrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contiene a todas las entidades principales, incluidos usuarios, grupos y carpetas.
ms.openlocfilehash: 847af7f719b15161738d488408ac11b81d9c57a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contiene a todas las entidades principales, incluidos usuarios, grupos y carpetas.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|prinGuid  <br/> |GUID, no nulo  <br/> |GUID de la entidad de seguridad. Se utiliza ampliamente como una clave principal alternativa porque su significado se cruza en el espacio de los servicios de dominio de Active Directory. (El GUID para una entidad de seguridad almacenada en caché es igual que el GUID del objeto de Active Directory correspondiente.)  <br/> |
|prinUri  <br/> |nvarchar (256), no nulo  <br/> |URI de la entidad de seguridad. La combinación SIP se utiliza para los usuarios y ma-grp se utiliza para casi todo lo demás.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nombre común. Utilizado sólo por tipos de usuario.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nombre para mostrar. Utilizado sólo por tipos de usuario.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nombre de la compañía. Utilizado sólo por tipos de usuario.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Correo electrónico. Utilizado sólo por tipos de usuario.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nombre de objeto de Active Directory que el principal es una versión en caché de dominio. Puede ser Null para tipos que no son objetos de Active Directory (por ejemplo, los usuarios del sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nombre principal de usuario del usuario (UPN). Utilizado sólo por tipos de usuario normal.  <br/> |
|prinDisabled  <br/> |smallint, no nulo  <br/> | 0: principal está activo. <br/>  1: principal está deshabilitado porque están deshabilitadas las capacidades SIP del usuario. <br/>  2: principal se ha eliminado porque se ha eliminado el objeto AD asociado. <br/> |
|prinTypeID  <br/> |smallint, no nulo  <br/> |Tipo principal (de tabla de tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype para asignación de grupo de negocio cliente del principal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valor de directiva persistente Chat Server para el usuario, si está presente la directiva del tipo de etiqueta.  <br/> |
|prinAddedBy  <br/> |int  <br/> |Identificador principal del creador.  <br/> |
|prinAddedOn  <br/> |bigint, no nulo  <br/> |Marca de tiempo para la hora de creación.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |Identificador de la entidad de seguridad que se actualizó por última vez esto.  <br/> |
|prinUpdatedOn  <br/> |bigint, no nulo  <br/> |Marca de tiempo de la última actualización.  <br/> |
|prinVerifiedOn  <br/> |fecha y hora, no nulo  <br/> |Fecha y hora de la última sincronización de Active Directory se actualización para la entidad de seguridad.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinTypeID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipalType.ptypeID.  <br/> |
   

