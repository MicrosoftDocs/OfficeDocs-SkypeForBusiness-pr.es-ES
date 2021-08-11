---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.
ms.openlocfilehash: fa90d112ce7b3397f055023034888b45bc5b8bcabc7948f7c4af0bb59788c2d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318693"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad  <br/> |
|invID  <br/> |int, no NULL  <br/> |Número secuencial único (por identificador de la entidad de seguridad) generado desde la tabla tblLastInviteId.  <br/> |
|nodeID  <br/> |int, no NULL  <br/> |Identificador de nodo (solo salón de chat).  <br/> |
|createdOn  <br/> |datetime, no NULL  <br/> |Momento de la creación.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
   

