---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: cf55ba04afe3688d3ecfd397dc4ffcbe50da2c19
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844073"
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

|**ID**|**Rol**|**Descripción**|**Usuario**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Cualquiera  <br/> |Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.  <br/> |Sí  <br/> |
|3  <br/> |AnyGroup  <br/> |Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Entidad de seguridad usada internamente por el servidor de chat persistente.  <br/> ||
|5  <br/> |Usuario  <br/> |Usuario habitual.  <br/> |Sí  <br/> |
|8   <br/> |DC  <br/> |Controlador de dominio de Servicios de dominio de Active Directory.  <br/> ||
|9   <br/> |Grupo  <br/> |Grupo de seguridad de Active Directory.  <br/> ||
|10  <br/> |Folder  <br/> |Unidad organizativa o contenedor de Active Directory.  <br/> ||
   
## <a name="see-also"></a>Consulte también

[tblPrincipal](tblprincipal.md)
