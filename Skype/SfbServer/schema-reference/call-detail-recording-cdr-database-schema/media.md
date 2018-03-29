---
title: Tabla Media
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medio utilizado en una sesión de peer-to-peer. Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio.
ms.openlocfilehash: 8833e7272c82dcbb7eef0da89d915680198589b5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="media-table"></a>Tabla Media
 
Cada registro representa un tipo de medio utilizado en una sesión de peer-to-peer. Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio.
  
> [!NOTE]
> La tabla de medios no debe utilizarse para calcular la duración media de una sesión. Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión. Intercambio de medios se realiza mediante la solicitud de invitación y StartTime indica el tiempo que se ha enviado la invitación. El tiempo de invitación no significa necesariamente la media de tiempo de inicio como media se inicia sólo después de que el sessionee acepta la sesión. La hora de finalización normalmente significa que la hora de finalización de esta sesión. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Principal, externa  <br/> |Número único que identifica este tipo de medio. Consulte la [tabla de MediaList](medialist.md) para obtener más información. <br/> |
|**Hora de inicio** <br/> |datetime  <br/> |Primary  <br/> |Esto es a la vez que se ha enviado una solicitud de los medios de comunicación, no la real media hora de inicio. **StartTime** incluye el tiempo de preparación de la sesión. <br/> |
|**Hora de finalización** <br/> |datetime  <br/> ||Se trata de la hora de finalización de la sesión.  <br/> |
   

