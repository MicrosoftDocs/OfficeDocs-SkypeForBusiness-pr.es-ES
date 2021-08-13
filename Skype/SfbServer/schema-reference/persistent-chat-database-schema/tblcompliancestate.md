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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315426"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no NULL  <br/> |ID del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no NULL  <br/> |Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Fecha y hora de expiración del bloqueo (si activeServerID no es -1).  <br/> |
   

