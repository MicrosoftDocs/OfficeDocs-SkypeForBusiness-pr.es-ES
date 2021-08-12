---
title: Tabla ConferenceJoinTimeThresholds en Skype Empresarial Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:'
ms.openlocfilehash: 9ce7e8e92921e0cccd8987d6f270a205c5c94de457571ebf959da703cc4bf2ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341755"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabla ConferenceJoinTimeThresholds en Skype Empresarial Server 2015
 
La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:
  
- Menos de 2 segundos.
    
- Entre 2 y 5 segundos.
    
- Entre 5 y 10 segundos.
    
- Más de 10 segundos.
    
La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |Entero  <br/> |Principal  <br/> |Identificador único de la clasificación.  <br/> |
|**ThresholdValue** <br/> |Entero  <br/> || Límite máximo de la clasificación. Los valores permitidos son: <br/>  2 <br/>  5  <br/>  10  <br/> |
   

