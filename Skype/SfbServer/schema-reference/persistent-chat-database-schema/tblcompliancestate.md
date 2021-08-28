---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580404"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no NULL  <br/> |ID del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no NULL  <br/> |Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Fecha y hora de expiración del bloqueo (si activeServerID no es -1).  <br/> |
   

