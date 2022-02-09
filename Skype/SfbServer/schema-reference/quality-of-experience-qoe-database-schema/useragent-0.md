---
title: Vista UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 22dcd5e127e123e027448ccddaa79007cfdbfe8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420823"
---
# <a name="useragent-view"></a>Vista UserAgent
 
La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |Entero  <br/> |Número único que identifica este agente de usuario.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuario. Consulta la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la UACategory CAA.  <br/> |
   

