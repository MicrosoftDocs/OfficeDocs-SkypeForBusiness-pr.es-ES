---
title: Tabla Media
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medios utilizado en una sesión de punto a punto. Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios.
ms.openlocfilehash: f0525b279fbef5cc7d4a1bc2ce0fce9212636a96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212940"
---
# <a name="media-table"></a>Tabla Media
 
Cada registro representa un tipo de medios utilizado en una sesión de punto a punto. Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios.
  
> [!NOTE]
> En la tabla de medios no debe usarse para calcular la duración media de una sesión. Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión. Intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica la hora en que se envió la invitación de la. El tiempo de invitar no significa necesariamente los medios de inicio de tiempo, debido a que los medios se inicia sólo después de la sessionee acepta la sesión. La hora de finalización normalmente significa que la hora de finalización de esta sesión. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Principal, externa  <br/> |Número único que identifica este tipo de medio. Consulte la [tabla MediaList](medialist.md) para obtener más información. <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Esta es la hora en que se ha enviado una solicitud de medios, no los medios reales y hora de inicio. **StartTime** incluye el tiempo de preparación de la sesión. <br/> |
|**EndTime** <br/> |datetime  <br/> ||Se trata de la hora de finalización de la sesión.  <br/> |
   

