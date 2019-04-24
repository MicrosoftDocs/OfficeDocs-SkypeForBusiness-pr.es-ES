---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212442"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, no es nulo  <br/> |Identificador del tipo de entidad de seguridad.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), no es nulo  <br/> |Descripción del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, no es nulo  <br/> |Es True si el tipo corresponde a las entidades de seguridad que se usan para fines internos.  <br/> |
|ptypeIsUser  <br/> |bit, no es nulo  <br/> |Es True si el tipo es un tipo de usuario.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|ptypeID  <br/> |Clave principal.  <br/> |
   
**Valores de la entidad de seguridad**

|**ID**|**Rol**|**Descripción**|**Usuario**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Cualquiera  <br/> |Entidad de seguridad genérico con ningún tipo conocido. No se usa en la tabla tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entidad de seguridad genérico de tipo de usuario. No se usa en la tabla tblPrincipal.  <br/> |Sí  <br/> |
|3  <br/> |AnyGroup  <br/> |Entidad de seguridad genérico con semántica de grupo. No se usa en la tabla tblPrincipal.  <br/> ||
|4  <br/> |Usuario del sistema  <br/> |Entidad de seguridad utilizada internamente por el servidor de Chat persistente.  <br/> ||
|5  <br/> |Usuario  <br/> |Usuario habitual.  <br/> |Sí  <br/> |
|8  <br/> |CONTROLADOR DE DOMINIO  <br/> |Controlador de dominio de servicios de dominio de Active Directory activo.  <br/> ||
|9  <br/> |Grupo  <br/> |Grupo de seguridad de Active Directory.  <br/> ||
|10  <br/> |Carpeta  <br/> |Contenedor de Active Directory o la unidad organizativa.  <br/> ||
   
## <a name="see-also"></a>Vea también

[tblPrincipal](tblprincipal.md)
