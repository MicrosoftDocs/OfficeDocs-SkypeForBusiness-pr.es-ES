---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contiene todos los principales, incluidos los usuarios, las carpetas y los grupos.
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295366"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contiene todos los principales, incluidos los usuarios, las carpetas y los grupos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|prinGuid  <br/> |GUID, not null  <br/> |GUID principal. Esto se usa ampliamente como una clave principal alternativa porque su significado pasa a ser el espacio de servicios de dominio de Active Directory. (El GUID de un principal en caché es igual al GUID de objeto de Active Directory correspondiente).  <br/> |
|prinUri  <br/> |nvarchar (256), not null  <br/> |URI principal. El esquema SIP se usa para los usuarios y el mA-GRP se usa para casi todos los demás.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nombre común. Solo se usan los tipos de usuario.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nombre para mostrar. Solo se usan los tipos de usuario.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nombre de la empresa. Solo se usan los tipos de usuario.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Correo electrónico. Solo se usan los tipos de usuario.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nombre de dominio del objeto de Active Directory del que el principal es una versión almacenada en caché. Puede ser null para los tipos que no son objetos de Active Directory (como usuarios del sistema).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nombre principal de usuario (UPN) del usuario. Solo lo usan los tipos de usuario normales.  <br/> |
|prinDisabled  <br/> |smallint, not null  <br/> | 0: la principal está activa. <br/>  1: la entidad de la identidad está deshabilitada porque las funciones SIP del usuario están deshabilitadas. <br/>  2: se eliminó el capital porque el objeto de AD asociado se ha eliminado. <br/> |
|prinTypeID  <br/> |smallint, not null  <br/> |Tipo principal (de la tabla tblPrincipalType).  <br/> |
|prinPoolID  <br/> |ENT  <br/> |Asignación de grupo de clientes de Skype empresarial para el principal.  <br/> |
|prinPolicyID  <br/> |ENT  <br/> |Valor de la Directiva del servidor de chat persistente para usuario, si la Directiva de tipo de etiqueta está presente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |IDENTIFICADOR principal del creador.  <br/> |
|prinAddedOn  <br/> |BIGINT, not null  <br/> |Marca de tiempo de la hora de creación.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |IDENTIFICADOR de la entidad de identidad que la actualizó por última vez.  <br/> |
|prinUpdatedOn  <br/> |BIGINT, not null  <br/> |Marca de tiempo de la última actualización.  <br/> |
|prinVerifiedOn  <br/> |DateTime, not null  <br/> |Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de identidad.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinTypeID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipalType. ptypeID.  <br/> |
   

