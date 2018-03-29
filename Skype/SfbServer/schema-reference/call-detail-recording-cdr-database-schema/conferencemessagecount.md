---
title: Tabla ConferenceMessageCount en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa a un usuario en una conferencia de mensajes Instantáneos e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabla ConferenceMessageCount en Skype para Business Server 2015
 
Cada registro de esta tabla representa a un usuario en una conferencia de mensajes Instantáneos e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros en esta tabla; un registro para cada usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de la conferencia. Se utiliza junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la instancia de la conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**ID de usuario** <br/> |int  <br/> |Externa  <br/> |Número único que identifica este usuario, se hace referenciado en la [tabla usuarios](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |El número de mensajes enviados por este usuario durante esta conferencia.  <br/> |
   

