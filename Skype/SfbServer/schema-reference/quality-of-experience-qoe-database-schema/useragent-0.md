---
title: Vista UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 942093ece5706115cc4e90171c09df8a8a169b09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907027"
---
# <a name="useragent-view"></a>Vista UserAgent
 
La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número único que identifica a este agente de usuario.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuario. Consulte la [tabla UserAgent](useragent.md) para obtener más detalles. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la CAA UACategory.  <br/> |
   

