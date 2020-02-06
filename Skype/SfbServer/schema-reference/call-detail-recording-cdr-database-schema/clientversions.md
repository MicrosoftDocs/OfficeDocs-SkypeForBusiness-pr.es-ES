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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815408"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabla ClientVersions en Skype empresarial Server 2015
 
La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |**nvarchar(256)** <br/> ||Nombre de la versión.  <br/> |
|**Tipocliente** <br/> |int  <br/> ||Especifica el tipo de cliente usado en la sesión. Para obtener más información, consulte la [tabla UserAgentDef](useragentdef.md) . <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

