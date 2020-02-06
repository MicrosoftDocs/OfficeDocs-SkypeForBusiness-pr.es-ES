---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene ámbitos asignados a los nodos.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812448"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contiene ámbitos asignados a los nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo al que se aplica el ámbito.  <br/> |
|scopePrinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|scopeIsDenied  <br/> |bit, not null  <br/> |Verdadero si el tipo de ámbito es denegar; False si la opción permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clave principal.  <br/> |
|scopeNodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeID.  <br/> |
|scopePrinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
   

