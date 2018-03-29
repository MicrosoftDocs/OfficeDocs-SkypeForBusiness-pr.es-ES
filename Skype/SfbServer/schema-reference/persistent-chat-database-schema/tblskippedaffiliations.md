---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se puede leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene las afiliaciones que no se puede leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|affDescription  <br/> |nvarchar (256), no nulo  <br/> |Cadena que identifica la afiliación.  <br/> El formato es: guid: uri de _{0}_ : _{1}_> id: _{2}_ <br/> |
|updatedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que actualiza esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es la única fuente de estas entradas.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

