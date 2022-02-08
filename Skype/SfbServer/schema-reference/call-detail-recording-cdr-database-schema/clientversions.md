---
title: Tabla ClientVersions en Skype Empresarial Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386329"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabla ClientVersions en Skype Empresarial Server 2015
 
La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principal  <br/> |Número único que identifica esta versión y este tipo de cliente.  <br/> |
|**Versión** <br/> |**nvarchar(256)** <br/> ||Nombre de la versión.  <br/> |
|**ClientType** <br/> |Entero  <br/> ||Especifica el tipo de cliente usado en la sesión. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

