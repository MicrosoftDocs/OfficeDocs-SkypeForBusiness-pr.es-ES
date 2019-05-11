---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929927"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Identificador de evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidad del servidor (correspondiente a la tabla tblServerIdentity.serverID).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|fanoutEventID  <br/> |Clave externa con búsqueda en la tabla Compliancedata.cmpleventid.  <br/> |
   

