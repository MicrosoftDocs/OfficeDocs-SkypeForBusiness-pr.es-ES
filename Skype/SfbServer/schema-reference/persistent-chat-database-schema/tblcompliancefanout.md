---
title: tblComplianceFanout
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
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.
ms.openlocfilehash: 34f1a5d7d6ea9f1f37e0f9e8d43159523f0f183a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623462"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |Entero  <br/> |Id. del evento  <br/> |
|fanoutServerID  <br/> |Entero  <br/> |Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|fanoutEventID  <br/> |Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.  <br/> |
   

