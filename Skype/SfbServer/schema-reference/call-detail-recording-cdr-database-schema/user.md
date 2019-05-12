---
title: Vista de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información acerca de los usuarios que han sido necesarios para las llamadas o las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930081"
---
# <a name="user-view"></a>Vista de usuario
 
La vista de usuario almacena información acerca de los usuarios que han sido necesarios para las llamadas o las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Número único que identifica a este usuario.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI del usuario.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Inquilino del usuario. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

