---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812938"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, not null  <br/> |IDENTIFICADOR de tipo de entidad de identidad.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), not null  <br/> |Descripción del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, not null  <br/> |True si el tipo corresponde a las entidades de identidad que se usan para fines internos.  <br/> |
|ptypeIsUser  <br/> |bit, not null  <br/> |True si el tipo es un tipo de usuario.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|ptypeID  <br/> |Clave principal.  <br/> |
   
**Valores principales**

|**ID**|**Rol**|**Descripción**|**Usuario**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Cualquiera  <br/> |Entidad de identidad genérica con un tipo no conocido. No se usa en la tabla tblPrincipal.  <br/> ||
|1  <br/> |AnyUser  <br/> |Identidad genérica del tipo de usuario. No se usa en la tabla tblPrincipal.  <br/> |Sí  <br/> |
|3  <br/> |AnyGroup  <br/> |Principal genérico con semántica de grupo. No se usa en la tabla tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal utilizado internamente por el servidor de chat persistente.  <br/> ||
|5  <br/> |Usuario  <br/> |Usuario normal.  <br/> |Sí  <br/> |
|4,8  <br/> |Clona  <br/> |Controlador de dominio de servicios de dominio de Active Directory.  <br/> ||
|99,999  <br/> |Mesa  <br/> |Grupo de seguridad de Active Directory.  <br/> ||
|base10  <br/> |Carpetas  <br/> |Contenedor de Active Directory o unidad de organización.  <br/> ||
   
## <a name="see-also"></a>Vea también

[tblPrincipal](tblprincipal.md)
