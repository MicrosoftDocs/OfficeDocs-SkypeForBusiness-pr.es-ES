---
title: Tabla ClientVersions en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898532"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabla ClientVersions en Skype para Business Server 2015
 
La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |**nvarchar(256)** <br/> ||Nombre de la versión.  <br/> |
|**TipoCliente** <br/> |int  <br/> ||Especifica el tipo de cliente utilizado en la sesión. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

