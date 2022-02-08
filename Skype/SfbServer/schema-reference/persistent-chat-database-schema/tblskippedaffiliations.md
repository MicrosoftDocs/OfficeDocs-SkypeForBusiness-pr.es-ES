---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso de servicios de dominio de Active Directory).
ms.openlocfilehash: b0996e3208e760c55b1b9d621d00e92a8e7a7112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394792"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso de servicios de dominio de Active Directory).
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad.  <br/> |
|affDescription  <br/> |nvarchar (256), no NULL  <br/> |Cadena que identifica la afiliación.  <br/> El formato es: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.  <br/> |
   
**Keys**

|**Columna(s)**|**Descripción**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

