---
title: Tabla multimedia
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.
ms.openlocfilehash: 4b2bb3252945b34a38e9a2863f82c517729e9f89
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385458"
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
   

