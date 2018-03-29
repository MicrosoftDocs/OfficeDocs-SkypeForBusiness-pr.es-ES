---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|principalID  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad asociada.  <br/> |
|affiliationID  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que representa la afiliación. Cada entidad de seguridad (excepto el sistema de tipos usuario) tiene también una afiliación por cuenta propia.  <br/> |
|índice  <br/> |int, no nulo  <br/> |Índice. El valor de afiliaciones automática es -1 y para las demás afiliaciones aumenta secuencialmente desde 1 dentro de cada \<principalID, affiliationId\> bote.  <br/> |
|updatedBy  <br/> |int, no nulo  <br/> |Entidad de seguridad que hizo la última actualización. Suele ser 1, que significa la sincronización de Active Directory.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|\<principalID, índice, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

