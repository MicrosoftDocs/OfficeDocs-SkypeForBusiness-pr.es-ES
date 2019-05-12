---
title: Tabla ConferenceMessageCount en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901432"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabla ConferenceMessageCount en Skype para Business Server 2015
 
Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de conferencia. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la instancia de conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |Número único que identifica a este usuario, de la [tabla de usuarios](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |El número de mensajes enviados por este usuario durante la conferencia.  <br/> |
   

