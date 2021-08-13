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
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de Servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 5eb67681e5823b8549deb01b44e0bcb771e26882a2cd713d9cf598ae0670335b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341675"
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

|**Columns**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clave principal.  <br/> |
|principalID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

