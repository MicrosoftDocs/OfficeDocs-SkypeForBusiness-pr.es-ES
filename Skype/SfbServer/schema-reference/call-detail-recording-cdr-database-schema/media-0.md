---
title: Vista de elementos multimedia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815058"
---
# <a name="media-view"></a>Vista de elementos multimedia
 
La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista de elementos multimedia no debe usarse para calcular la duración multimedia de una sesión. Esta vista contiene los detalles de señalización de intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los medios solo se inician una vez que se acepta la sesión. 
  
La vista de elementos multimedia contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) , además de las que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de medio. Para obtener más información, consulte la [tabla](medialist.md) de la información. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Hora en que se envió una solicitud de medios.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
   

