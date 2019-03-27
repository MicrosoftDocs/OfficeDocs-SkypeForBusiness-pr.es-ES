---
title: Tabla taba en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe de resumen de tiempo de unirse a conferencia resume la cantidad de tiempo necesario para que los usuarios correctamente unirse a una conferencia; Estos valores de tiempo se notifican como una media y en una de las siguientes categorías:'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895820"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabla taba en Skype para Business Server 2015
 
La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe de resumen de tiempo de unirse a conferencia resume la cantidad de tiempo necesario para que los usuarios correctamente unirse a una conferencia; Estos valores de tiempo se notifican como una media y en una de las siguientes categorías:
  
- Menos de 2 segundos.
    
- Entre 2 y 5 segundos.
    
- Entre 5 y 10 segundos.
    
- Más de 10 segundos.
    
La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.
  
En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Identificador único para la clasificación.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Límite superior para la clasificación. Los valores permitidos son: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

