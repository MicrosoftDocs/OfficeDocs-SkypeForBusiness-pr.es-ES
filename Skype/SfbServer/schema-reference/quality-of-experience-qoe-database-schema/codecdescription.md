---
title: Tabla CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec únicos a su códec correspondiente. Los códecs se usan para codificar las señales digitales de transmisión y difusión y, después, descodificar esas señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810368"
---
# <a name="codecdescription-table"></a>Tabla CodecDescription
 
La tabla CodecDescription asigna identificadores de códec únicos a su códec correspondiente. Los códecs se usan para codificar las señales digitales de transmisión y difusión y, después, descodificar esas señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Identificador único asignado al códec.  <br/> |
|**CodecDescription** <br/> |VARCHAR (256)  <br/> |Solo  <br/> |Descripción única del códec correspondiente al CodecDescriptionKey.  <br/> |
   

