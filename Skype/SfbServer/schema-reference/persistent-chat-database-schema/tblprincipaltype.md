---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831540"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, no NULL  <br/> |Id. del tipo de entidad de seguridad  <br/> |
|ptypeDesc  <br/> |nvarchar (256), no NULL  <br/> |Descripción del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, no NULL  <br/> |Verdadero si el tipo corresponde a las entidades de seguridad utilizadas para fines internos.  <br/> |
|ptypeIsUser  <br/> |bit, no NULL  <br/> |Verdadero si el tipo es un tipo de usuario.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|ptypeID  <br/> |Clave principal.  <br/> |
   
**Valores de las entidades de seguridad**

|**Id.**|**Rol**|**Descripción**|**Usuario**|
|:-----|:-----|:-----|:-----|
|1   <br/> |Cualquiera  <br/> |Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.  <br/> ||
|2   <br/> |AnyUser  <br/> |Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.  <br/> |Sí  <br/> |
|3   <br/> |AnyGroup  <br/> |Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.  <br/> ||
|4   <br/> |SystemUser  <br/> |Entidad de seguridad usada internamente por el servidor de chat persistente.  <br/> ||
|5   <br/> |User  <br/> |Usuario habitual.  <br/> |Sí  <br/> |
|8   <br/> |DC  <br/> |Controlador de dominio de Servicios de dominio de Active Directory.  <br/> ||
|9   <br/> |Group  <br/> |Grupo de seguridad de Active Directory.  <br/> ||
|10    <br/> |Folder  <br/> |Unidad organizativa o contenedor de Active Directory.  <br/> ||
   
## <a name="see-also"></a>Vea también

[tblPrincipal](tblprincipal.md)
