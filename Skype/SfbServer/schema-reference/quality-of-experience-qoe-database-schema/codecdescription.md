---
title: Tabla CodecDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna los identificadores de códecs únicos al códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y, a continuación, descodificar esas señales para la reproducción. En esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212273"
---
# <a name="codecdescription-table"></a>Tabla CodecDescription
 
La tabla CodecDescription asigna los identificadores de códecs únicos al códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y, a continuación, descodificar esas señales para la reproducción. En esta tabla se introdujo en Microsoft Lync Server 2013
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**A CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Identificador único asignado a códec.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Único  <br/> |Descripción única del códec correspondiente a CodecDescriptionKey.  <br/> |
   

