---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812018"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|affDescription  <br/> |nvarchar (256), not null  <br/> |Una cadena que identifica la afiliación.  <br/> El formato es: GUID: _{0}_ uri: _{1}_> ID:_{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.  <br/> |
   
**Sus**

|**Columna (s)**|**Descripción**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
   

