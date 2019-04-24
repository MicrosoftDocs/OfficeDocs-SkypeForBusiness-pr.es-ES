---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212631"
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
   

