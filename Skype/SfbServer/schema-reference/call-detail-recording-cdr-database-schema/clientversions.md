---
title: Tabla ClientVersions en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296514"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabla ClientVersions en Skype empresarial Server 2015
 
La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |**nvarchar(256)** <br/> ||Nombre de la versión.  <br/> |
|**Tipocliente** <br/> |int  <br/> ||Especifica el tipo de cliente usado en la sesión. Para obtener más información, consulte la [tabla UserAgentDef](useragentdef.md) . <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

