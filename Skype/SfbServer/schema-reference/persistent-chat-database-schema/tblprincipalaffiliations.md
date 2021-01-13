---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias a ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815870"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias a ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|principalID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad afiliada.  <br/> |
|affiliationID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.  <br/> |
|index  <br/> |int, no NULL  <br/> |Índice. El valor de las afiliaciones automáticas es -1 y para las demás afiliaciones aumenta secuencialmente de 1 dentro de cada \<principalID, affiliationId\> depósito.  <br/> |
|updatedBy  <br/> |int, no NULL  <br/> |Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.  <br/> |
   
**Keys**

|**Columns**|**Descripción**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

