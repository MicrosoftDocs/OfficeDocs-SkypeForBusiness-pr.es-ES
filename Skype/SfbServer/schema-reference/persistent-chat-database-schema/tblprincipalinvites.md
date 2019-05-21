---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295296"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|invID  <br/> |int, not null  <br/> |Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.  <br/> |
|nodeID  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo (solo salón de chat).  <br/> |
|creado  <br/> |DateTime, not null  <br/> |Momento de la creación.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
|nodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeID.  <br/> |
   

