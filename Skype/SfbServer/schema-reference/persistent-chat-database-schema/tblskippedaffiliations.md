---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se podrían leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924944"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene las afiliaciones que no se podrían leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|affDescription  <br/> |nvarchar (256), no es nulo  <br/> |Una cadena que identifica la afiliación.  <br/> El formato es: guid: _{0}_ uri: _{1}_> identificador:_{2}_ <br/> |
|updatedBy  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (los usuarios del sistema) debido a que la sincronización de Active Directory es el único origen para estas entradas.  <br/> |
   
**Claves**

|**Columnas**|**Descripción**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

