---
title: Tabla CodecDescription
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec único su códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y después descifran las señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a>Tabla CodecDescription
 
La tabla CodecDescription asigna identificadores de códec único su códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y después descifran las señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Identificador único asignado al códec.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Único  <br/> |Descripción única del códec correspondiente a la CodecDescriptionKey.  <br/> |
   

