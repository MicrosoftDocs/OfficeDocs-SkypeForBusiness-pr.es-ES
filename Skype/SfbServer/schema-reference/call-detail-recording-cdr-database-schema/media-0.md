---
title: Vista de elementos multimedia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista de elementos multimedia almacena información acerca de un tipo de medio utilizado en una sesión de punto a punto. Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930696"
---
# <a name="media-view"></a>Vista de elementos multimedia
 
La vista de elementos multimedia almacena información acerca de un tipo de medio utilizado en una sesión de punto a punto. Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista de elementos multimedia no debe usarse para calcular la duración media de una sesión. Esta vista contiene los detalles de señalización de intercambio de medios en una sesión. Intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica la hora en que se envió la invitación de la. El tiempo de invitar no significa necesariamente los medios de inicio de tiempo, debido a que los medios se inicia sólo después de la sesión se acepta. 
  
La vista de elementos multimedia todas las columnas en la [vista SessionDetails](sessiondetails-0.md) contiene además de los que aparecen a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de medio. Consulte la [tabla MediaList](medialist.md) para obtener más información. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Hora en que se ha enviado una solicitud de medios.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
   

