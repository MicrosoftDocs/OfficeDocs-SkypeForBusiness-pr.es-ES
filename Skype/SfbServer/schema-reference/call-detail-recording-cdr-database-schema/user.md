---
title: Vista de usuario
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a>Vista de usuario
 
La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|ID de usuario  <br/> |int  <br/> |Número único que identifica este usuario.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI del usuario.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Inquilinos del usuario. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
   

