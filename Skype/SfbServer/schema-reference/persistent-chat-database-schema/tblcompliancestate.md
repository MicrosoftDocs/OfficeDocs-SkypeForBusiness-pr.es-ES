---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento de normas de todo el grupo.
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento de normas de todo el grupo.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no nulo  <br/> |Id. del evento transformados de conformidad más reciente.  <br/> |
|activeServerID  <br/> |int, no nulo  <br/> |Identificador del servidor de cumplimiento mantiene el bloqueo exclusivo en la base de datos, o -1 si no hay ninguno.  <br/> |
|lockExpirationTime  <br/> |DateTime2, no nulo  <br/> |Bloquear tiempo de caducidad (si activeServerID no es -1).  <br/> |
   

