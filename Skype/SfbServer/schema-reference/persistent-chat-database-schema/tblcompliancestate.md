---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 6b7f2af97ab25fc7ad2320921941cc7b1828aa1e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746526"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no NULL  <br/> |ID del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no NULL  <br/> |Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Fecha y hora de expiración del bloqueo (si activeServerID no es -1).  <br/> |
   

