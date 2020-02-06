---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814478"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|principalID  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad afiliada.  <br/> |
|affiliationID  <br/> |int, not null  <br/> |IDENTIFICADOR de la identidad que representa la afiliación. Cada principal (excepto los tipos de usuario del sistema) tiene también una afiliación propia.  <br/> |
|clasificación  <br/> |int, not null  <br/> |Clasificación. El valor de las afiliaciones automáticas es de-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada \<PrincipalID, affiliationId\> bucket.  <br/> |
|updatedBy  <br/> |int, not null  <br/> |Principal que realizó la actualización más reciente. Esto suele ser 1, que significa sincronización de Active Directory.  <br/> |
   
**Sus**

|**Columnas**|**Descripción**|
|:-----|:-----|
|\<principalID, Indice, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
|affiliationID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
   

