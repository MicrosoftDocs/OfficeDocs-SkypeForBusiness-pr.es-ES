---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420883"
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
   

