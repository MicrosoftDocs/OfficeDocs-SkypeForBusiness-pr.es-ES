---
title: Vista McuJoinsAndLeaves
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vista McuJoinsAndLeaves almacena información acerca de la participación de los usuarios y deje la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de llamadas sobre una combinación de un servidor de conferencias o deje y join de usuario. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: db759e324689cfbad92389f30c8fd632c24ebd5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892811"
---
# <a name="mcujoinsandleaves-view"></a>Vista McuJoinsAndLeaves
 
La vista McuJoinsAndLeaves almacena información acerca de la participación de los usuarios y deje la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de llamadas sobre una combinación de un servidor de conferencias o deje y join de usuario. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la instancia de conferencia. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencia que el usuario conectado a.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencia que el usuario conectado a. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |El URI del usuario cuya información / salida del servidor de conferencia que se ha capturado.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |El tipo de URI del usuario cuya información / salida del servidor de conferencia que se ha capturado. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario que se ha capturado cuya información / salida del servidor de conferencia. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La versión del cliente usado por el usuario que se ha capturado cuya información / salida del servidor de conferencia.  <br/> |
|**UserClientType** <br/> |int  <br/> |El cliente usado por el usuario que se ha capturado cuya información / salida del servidor de conferencia. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |El nombre de la categoría del cliente usado por el usuario que se ha capturado cuya información / salida del servidor de conferencia.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica la combinación usuario/dispositivo para usuarios que han iniciado sesión simultáneamente varios dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que representa si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador del cuadro de diálogo SIP de la sesión. El formato es: cuadro de diálogo; de etiqueta; para la etiqueta.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Tiempo que el usuario se unió al servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |El usuario abandonó el servidor de conferencia de tiempo.  <br/> |
   

