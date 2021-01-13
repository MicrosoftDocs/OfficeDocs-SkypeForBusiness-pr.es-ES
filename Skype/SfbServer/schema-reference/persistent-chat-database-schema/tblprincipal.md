---
title: tblPrincipal
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
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: La tabla tblPrincipal contiene todas las entidades de seguridad, incluidos usuarios, carpetas y grupos.
ms.openlocfilehash: ee9e16d0fcd5d7206bb73ff8b13cdc9d930b6b97
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815900"
---
# <a name="tblprincipal"></a>tblPrincipal
 
La tabla tblPrincipal contiene todas las entidades de seguridad, incluidos usuarios, carpetas y grupos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad.  <br/> |
|prinGuid  <br/> |GUID, no NULL  <br/> |GUID principal. Esto se usa ampliamente como clave principal alternativa porque su significado se cruza en el espacio de Servicios de dominio de Active Directory. (El GUID de una entidad de seguridad almacenada en caché es igual al GUID del objeto de Active Directory correspondiente).  <br/> |
|prinUri  <br/> |nvarchar (256), no NULL  <br/> |URI de la entidad de seguridad. El esquema SIP se usa para los usuarios, mientras que ma-grp se usa para prácticamente todo lo demás.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nombre común. Usado solo por los tipos de usuario.  <br/> |
|prinDisplayName  <br/> |nvarchar (256)  <br/> |Nombre para mostrar. Usado solo por los tipos de usuario.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nombre de la compañía. Usado solo por los tipos de usuario.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Correo electrónico. Usado solo por los tipos de usuario.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nombre de dominio del objeto de Active Directory del que la entidad de seguridad es una versión en caché. Puede tener un valor NULL en los tipos que no sean objetos de Active Directory (por ejemplo, usuarios de sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nombre principal de usuario (UPN) del usuario. Usado solo por los tipos de usuario normales.  <br/> |
|prinDisabled  <br/> |smallint, no NULL  <br/> | 0: la entidad de seguridad está activa. <br/>  1: La entidad de seguridad está deshabilitada porque las capacidades SIP del usuario están deshabilitadas. <br/>  2: la entidad de seguridad se elimina porque el objeto de AD asociado se ha eliminado. <br/> |
|prinTypeID  <br/> |smallint, no NULL  <br/> |Tipo de la entidad de seguridad (de la tabla tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Asignación del grupo de clientes de Skype Empresarial para la entidad de seguridad.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valor de directiva de servidor de chat persistente para el usuario, si la directiva de tipo de etiqueta está presente.  <br/> |
|prinAddedBy  <br/> |entero  <br/> |Identificador de la entidad de seguridad del creador.  <br/> |
|prinAddedOn  <br/> |bigint, no NULL  <br/> |Marca de tiempo de la hora de creación.  <br/> |
|prinUpdatedBy  <br/> |entero  <br/> |Identificador de la entidad de seguridad que actualizó esto por última vez.  <br/> |
|prinUpdatedOn  <br/> |bigint, no NULL  <br/> |Marca de tiempo de la última actualización.  <br/> |
|prinVerifiedOn  <br/> |datetime, no NULL  <br/> |Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de seguridad.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinTypeID  <br/> |Clave externa con búsqueda en la tabla tblPrincipalType.ptypeID.  <br/> |
   

