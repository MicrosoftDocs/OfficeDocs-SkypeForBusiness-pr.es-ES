---
title: Vista de McuJoinsAndLeaves
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vista McuJoinsAndLeaves almacena información acerca de la combinación de los usuarios y dejar la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de la llamada acerca de una combinación de un servidor de conferencias o vacaciones y combinación de usuario. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 77045d852708cd7d8ceb0da473032485e130ea50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-view"></a>Vista de McuJoinsAndLeaves
 
La vista McuJoinsAndLeaves almacena información acerca de la combinación de los usuarios y dejar la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de la llamada acerca de una combinación de un servidor de conferencias o vacaciones y combinación de usuario. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de la conferencia. Se utiliza junto con SessionIdSeq para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la instancia de la conferencia. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencias que el usuario conectado a.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencias que el usuario conectado a. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |El URI del usuario cuya información de combinación o abandonarlo conferencing server fue capturada.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |El tipo de URI del usuario cuya información de combinación o abandonarlo conferencing server fue capturada. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario cuya información de combinación o abandonarlo conferencing server fue capturada. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La versión de cliente utilizada por el usuario cuya información de combinación o abandonarlo conferencing server fue capturada.  <br/> |
|**UserClientType** <br/> |int  <br/> |El cliente utilizado el usuario cuya información de combinación o abandonarlo conferencing server fue capturada. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |El nombre de la categoría del cliente utilizado por el usuario cuya información de combinación o abandonarlo conferencing server fue capturada.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica la combinación usuario/dispositivo de usuarios conectados simultáneamente a varios dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que indica si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo SIP de la sesión. El formato es: diálogo de etiqueta; a la etiqueta.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Tiempo que el usuario participó en el servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Vez que el usuario dejado el servidor de conferencia.  <br/> |
   

