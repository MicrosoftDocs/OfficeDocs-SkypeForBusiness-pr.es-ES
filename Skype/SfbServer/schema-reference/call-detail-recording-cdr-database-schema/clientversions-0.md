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
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296542"
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
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, la Conferencing_Attendant_ de cliente 1.0 pertenece a la CAA de ClientCategory.  <br/> |
   

