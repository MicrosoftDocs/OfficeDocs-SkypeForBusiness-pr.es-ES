---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de Servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 66772bafe362d8298b5c926f94a2362f248e5fa6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767351"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de Servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|principalID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad afiliada.  <br/> |
|affiliationID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.  <br/> |
|index  <br/> |int, no NULL  <br/> |Índice. El valor de las autoafiliaciones es -1 y para las demás afiliaciones aumenta secuencialmente de 1 dentro de cada \<principalID, affiliationId\> cubo.  <br/> |
|updatedBy  <br/> |int, no NULL  <br/> |Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.  <br/> |
   
**Keys**

|**Columns**|**Descripción**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

