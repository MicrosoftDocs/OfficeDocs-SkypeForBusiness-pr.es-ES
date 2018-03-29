---
title: Vista de ClientVersions
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información acerca de los diversos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a>Vista de ClientVersions
 
La vista ClientVersions almacena información acerca de los diversos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Pueden haber varios registros para ciertas columnas. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |nvarchar(256)  <br/> |Representa al agente de usuario.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, el cliente que pertenece el CAA ClientCategory Conferencing_Attendant_1.0.  <br/> |
   

