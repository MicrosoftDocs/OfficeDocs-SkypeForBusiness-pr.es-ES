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
ms.openlocfilehash: 200280f6a82a50490aee77177464b435e647a0a44852ca0db5b59c64bda836f3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302254"
---
# <a name="user-view"></a>Vista de usuario
 
La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|UserId  <br/> |Entero  <br/> |Número único que identifica a este usuario.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI del usuario.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Inquilino del usuario. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI de usuario. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

