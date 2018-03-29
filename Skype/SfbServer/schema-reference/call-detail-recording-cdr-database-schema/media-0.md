---
title: Vista de elementos multimedia
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista de elementos multimedia almacena información sobre un tipo de medio utilizado en una sesión de peer-to-peer. Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a>Vista de elementos multimedia
 
La vista de elementos multimedia almacena información sobre un tipo de medio utilizado en una sesión de peer-to-peer. Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista de elementos multimedia no debe utilizarse para calcular la duración media de una sesión. Esta vista contiene los detalles de señalización de intercambio de medios en una sesión. Intercambio de medios se realiza mediante la solicitud de invitación y StartTime indica el tiempo que se ha enviado la invitación. El tiempo de invitación no significa necesariamente la media de tiempo de inicio como media se inicia después de la sesión se acepta. 
  
La vista de elementos multimedia contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además los mencionados a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de medio. Consulte la [tabla de MediaList](medialist.md) para obtener más información. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Hora en que se ha enviado una solicitud de los medios de comunicación.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
   

