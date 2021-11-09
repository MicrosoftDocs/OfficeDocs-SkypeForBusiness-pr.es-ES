---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
ms.openlocfilehash: 96b603ac859664163339a9c5628bdec394881657
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854045"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no NULL  <br/> |ID del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no NULL  <br/> |Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Fecha y hora de expiración del bloqueo (si activeServerID no es -1).  <br/> |
   

