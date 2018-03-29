---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que se procesan un evento de conformidad.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout contiene todos los servidores que se procesan un evento de conformidad.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID de evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidad del servidor (correspondiente a la tabla de tblServerIdentity.serverID).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|fanoutEventID  <br/> |Clave externa con la búsqueda en la tabla tblComplianceData.cmplEventID.  <br/> |
   

