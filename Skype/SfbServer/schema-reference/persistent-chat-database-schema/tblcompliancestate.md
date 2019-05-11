---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929850"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento de todo el grupo de servidores.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, no es nulo  <br/> |Identificador del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, no es nulo  <br/> |Identificador del servidor de cumplimiento de normas que mantiene el bloqueo exclusivo en la base de datos, o -1 si no hay ninguno.  <br/> |
|lockExpirationTime  <br/> |DateTime2, no es nulo  <br/> |Bloquear el tiempo de expiración (si activeServerID no es -1).  <br/> |
   

