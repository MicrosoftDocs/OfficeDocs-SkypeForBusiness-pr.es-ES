---
title: Vista ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro en la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213399"
---
# <a name="clientversions-view"></a>Vista ClientVersions
 
La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro en la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Pueden haber varios registros para determinadas columnas. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |nvarchar(256)  <br/> |Representa al agente de usuario.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA ClientCategory.  <br/> |
   

