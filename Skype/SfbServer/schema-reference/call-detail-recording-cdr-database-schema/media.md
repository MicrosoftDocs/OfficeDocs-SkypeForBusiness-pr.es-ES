---
title: Tabla multimedia
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.
ms.openlocfilehash: 095e1f3227bbaf3335f581acbebbddaccd6b73de33639b2a0d04302a5c104393
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322952"
---
# <a name="media-table"></a>Tabla multimedia
 
Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.
  
> [!NOTE]
> No debe usarse la tabla Media para calcular la duración de los medios de una sesión. Esta tabla contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que el participante de la sesión acepta la sesión. Por lo general, EndTime implica la hora de finalización de esta sesión. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Principal, Exterior  <br/> |Número único que identifica este tipo de medios. Vea la [tabla MediaList](medialist.md) para obtener más información. <br/> |
|**StartTime** <br/> |datetime  <br/> |Principal  <br/> |Hora a la que se envió una solicitud de medios, no la hora de inicio real de los medios. **StartTime** incluye el tiempo de establecimiento de la sesión.<br/> |
|**EndTime** <br/> |datetime  <br/> ||Hora de finalización de la sesión.  <br/> |
   

