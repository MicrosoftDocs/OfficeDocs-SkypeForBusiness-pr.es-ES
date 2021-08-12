---
title: Vista multimedia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 9e1165e19db4d007f04007233a7751a9119fcf310cf61b257e7e5014599357c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322962"
---
# <a name="media-view"></a>Vista multimedia
 
La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión. 
  
La vista Multimedia contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de medio. Vea la [tabla MediaList](medialist.md) para obtener más información. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Hora a la que se envió la solicitud de medios.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
   

