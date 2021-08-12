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
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282992"
---
# <a name="useragent-view"></a>Vista UserAgent
 
La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |Entero  <br/> |Número único que identifica este agente de usuario.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuario. Consulta la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la UACategory CAA.  <br/> |
   

