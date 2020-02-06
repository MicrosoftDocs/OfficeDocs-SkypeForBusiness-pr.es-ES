---
title: Vista ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815418"
---
# <a name="clientversions-view"></a>Vista ClientVersions
 
La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> Es posible que haya varios registros para determinadas columnas. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número único que identifica este tipo de cliente y versión.  <br/> |
|**Versión** <br/> |nvarchar(256)  <br/> |Representa el agente de usuario.  <br/> |
|**Tipocliente** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA de ClientCategory.  <br/> |
   

