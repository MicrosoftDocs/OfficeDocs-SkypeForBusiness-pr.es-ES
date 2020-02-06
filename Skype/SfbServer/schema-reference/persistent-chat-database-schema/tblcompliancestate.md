---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento para todo el grupo.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814638"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contiene información de estado de cumplimiento para todo el grupo.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |BIGINT, not null  <br/> |IDENTIFICADOR del último evento de cumplimiento procesado.  <br/> |
|activeServerID  <br/> |int, not null  <br/> |IDENTIFICADOR del servidor de cumplimiento que contiene el bloqueo exclusivo de la base de datos, o bien-1 si no hay ninguno.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Fecha de expiración de bloqueo (si activeServerID no es-1).  <br/> |
   

