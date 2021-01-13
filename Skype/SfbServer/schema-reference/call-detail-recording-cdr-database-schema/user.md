---
title: Vista de usuario
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831700"
---
# <a name="user-view"></a>Vista de usuario
 
La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserId  <br/> |entero  <br/> |Número único que identifica a este usuario.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI del usuario.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Inquilino del usuario. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI de usuario. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

