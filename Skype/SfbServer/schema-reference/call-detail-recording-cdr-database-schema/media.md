---
title: Tabla Media
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296010"
---
# <a name="media-table"></a>Tabla Media
 
Cada registro representa un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.
  
> [!NOTE]
> La tabla de medios no se debe usar para calcular la duración multimedia de una sesión. Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los elementos multimedia solo se inician después de que la sesión acepte la sesión. La EndTime normalmente significa la hora de finalización de esta sesión. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**MediaId** <br/> |tinyint  <br/> |Principal, extranjero  <br/> |Número único que identifica este tipo de medio. Para obtener más información, consulte la [tabla](medialist.md) de la información. <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Este es el tiempo que se envió una solicitud de medios, no la hora real de inicio de medios. **StartTime** incluye la hora de configuración de la sesión. <br/> |
|**EndTime** <br/> |datetime  <br/> ||Esta es la hora de finalización de la sesión.  <br/> |
   

