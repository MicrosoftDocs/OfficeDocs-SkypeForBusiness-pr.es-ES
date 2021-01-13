---
title: Vista ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813360"
---
# <a name="clientversions-view"></a>Vista ClientVersions
 
La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Puede haber varios registros para determinadas columnas. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**VersionId** <br/> |entero  <br/> |Número único de identificación de esta versión y este tipo de cliente.  <br/> |
|**Versión** <br/> |nvarchar(256)  <br/> |Representa el agente de usuario.  <br/> |
|**ClientType** <br/> |entero  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a ClientCategory CAA.  <br/> |
   

