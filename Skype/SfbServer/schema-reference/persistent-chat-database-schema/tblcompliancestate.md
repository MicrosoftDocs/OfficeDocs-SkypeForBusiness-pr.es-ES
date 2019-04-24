---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212638"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no es nulo  <br/> |Identificador del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no es nulo  <br/> |Identificador del servidor de cumplimiento de normas que mantiene el bloqueo exclusivo en la base de datos, o -1 si no hay ninguno.  <br/> |
|lockExpirationTime  <br/> |DateTime2, no es nulo  <br/> |Bloquear el tiempo de expiración (si activeServerID no es -1).  <br/> |
   

