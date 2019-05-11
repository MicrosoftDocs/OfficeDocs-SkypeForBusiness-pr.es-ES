---
title: Tabla taba en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe de resumen de tiempo de unirse a conferencia resume la cantidad de tiempo necesario para que los usuarios correctamente unirse a una conferencia; Estos valores de tiempo se notifican como una media y en una de las siguientes categorías:'
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901439"
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
   

