---
title: Vista UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800020"
---
# <a name="useragent-view"></a>Vista UserAgent
 
La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |entero  <br/> |Número único que identifica este agente de usuario.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuario. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la UACategory CAA.  <br/> |
   

