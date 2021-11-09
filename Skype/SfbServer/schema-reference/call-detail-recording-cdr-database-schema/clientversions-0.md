---
title: Vista ClientVersions
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 7e44806e817c6010bb9d14ff2f29c118ac9a290b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854194"
---
# <a name="clientversions-view"></a>Vista ClientVersions
 
La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Puede haber varios registros para determinadas columnas. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**VersionId** <br/> |Entero  <br/> |Número único de identificación de esta versión y este tipo de cliente.  <br/> |
|**Versión** <br/> |nvarchar(256)  <br/> |Representa el agente de usuario.  <br/> |
|**ClientType** <br/> |Entero  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a ClientCategory CAA.  <br/> |
   

