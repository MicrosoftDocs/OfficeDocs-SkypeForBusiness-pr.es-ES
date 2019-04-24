---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212505"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|principalID  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad afiliado.  <br/> |
|affiliationID  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que representa la afiliación. Cada entidad de seguridad (excepto system-usuario-types) tiene también un afiliación Self.  <br/> |
|índice  <br/> |int, no es nulo  <br/> |Índice. El valor de afiliaciones Self es -1, y para las demás afiliaciones aumenta secuencialmente desde 1 dentro de cada uno de ellos \<principalID, affiliationId\> bucket.  <br/> |
|updatedBy  <br/> |int, no es nulo  <br/> |Entidad de seguridad que hizo la actualización más reciente. Generalmente es 1, lo que significa que la sincronización de Active Directory.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

