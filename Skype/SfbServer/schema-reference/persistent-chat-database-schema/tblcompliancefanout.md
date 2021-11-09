---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: a4b17a234b8efe1b661c1ebbe31a8ed34b0d5935
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854104"
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
   

