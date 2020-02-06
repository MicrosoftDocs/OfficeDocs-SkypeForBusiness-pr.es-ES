---
title: Vista UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805088"
---
# <a name="useragent-view"></a>Vista UserAgent
 
La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número único que identifica a este agente de usuario.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuario. Para obtener más información, consulta la [tabla UserAgent](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1,0 pertenece a la CAA de UACategory.  <br/> |
   

