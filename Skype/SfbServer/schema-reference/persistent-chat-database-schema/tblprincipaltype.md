---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene tipos principales para clasificar lo que está en la tabla tblPrincipal.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contiene tipos principales para clasificar lo que está en la tabla tblPrincipal.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, no nulo  <br/> |Identificador del tipo de entidad de seguridad.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), no nulo  <br/> |Descripción del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bits, no nulo  <br/> |True si el tipo corresponde a los principales que se usan para propósitos internos.  <br/> |
|ptypeIsUser  <br/> |bits, no nulo  <br/> |True si el tipo es un tipo de usuario.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|ptypeID  <br/> |Clave principal.  <br/> |
   
**Valores de la entidad de seguridad**

|**ID.**|**Rol**|**Descripción**|**Usuario**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Cualquiera  <br/> |Principal genérico con ningún tipo conocido. No se utiliza en la tabla tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Principal genérico del tipo de usuario. No se utiliza en la tabla tblPrincipal.  <br/> |Sí  <br/> |
|3  <br/> |AnyGroup  <br/> |Principal genérico con grupo semántico. No se utiliza en la tabla tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal utilizado internamente por el servidor de charla persistente.  <br/> ||
|5  <br/> |Usuario  <br/> |Usuario normal.  <br/> |Sí  <br/> |
|8  <br/> |CONTROLADOR DE DOMINIO  <br/> |Controlador de dominio de servicios de dominio de directorio activo.  <br/> ||
|9  <br/> |Grupo  <br/> |Grupo de seguridad de Active Directory.  <br/> ||
|10  <br/> |Carpeta  <br/> |Contenedor de Active Directory o la unidad organizativa.  <br/> ||
   
## <a name="see-also"></a>Vea también

#### 

[tblPrincipal](tblprincipal.md)

