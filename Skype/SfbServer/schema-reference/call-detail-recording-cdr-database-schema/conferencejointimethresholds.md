---
title: Tabla ConferenceJoinTimeThresholds en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe resumen de conferencia combinación resume la cantidad de tiempo requerido por los usuarios a unirse a una conferencia; Estos valores de tiempo se notifican como promedio y en una de las siguientes categorías:'
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabla ConferenceJoinTimeThresholds en Skype para Business Server 2015
 
La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe resumen de conferencia combinación resume la cantidad de tiempo requerido por los usuarios a unirse a una conferencia; Estos valores de tiempo se notifican como promedio y en una de las siguientes categorías:
  
- Menos de 2 segundos.
    
- Entre el segundo 2 y 5 segundos.
    
- Entre 5 y 10 segundos.
    
- Más de 10 segundos.
    
La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Identificador único para la clasificación.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Límite superior de la clasificación. Los valores permitidos son: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

