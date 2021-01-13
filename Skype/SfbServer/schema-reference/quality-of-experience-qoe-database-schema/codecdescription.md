---
title: Tabla CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes. Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831350"
---
# <a name="codecdescription-table"></a>Tabla CodecDescription
 
La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes. Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principal  <br/> |Identificador único asignado a códec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Única  <br/> |Descripción única del códec que corresponde a CodecDescriptionKey.  <br/> |
   

