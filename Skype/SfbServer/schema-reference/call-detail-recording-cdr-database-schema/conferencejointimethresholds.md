---
title: Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia. En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296500"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015
 
La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia. En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:
  
- Menos de 2 segundos.
    
- Entre 2 y 5 segundos.
    
- Entre 5 segundos y 10 segundos.
    
- Más de 10 segundos.
    
La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Identificador único de la clasificación.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Límite superior de la clasificación. Los valores permitidos son: <br/>  2 <br/>  5 <br/>  base10 <br/> |
   

