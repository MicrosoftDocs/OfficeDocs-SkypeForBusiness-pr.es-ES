---
title: Vista de FocusJoinsAndLeaves
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vista FocusJoinsAndLeaves almacena información acerca de la combinación y dejar información para una conferencia. Cada conferencia se representa en esta vista mediante un registro escrito cada vez que un usuario se une y abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 3ae234977ef541ca523178f41b40f12135b16bfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-view"></a>Vista de FocusJoinsAndLeaves
 
La vista FocusJoinsAndLeaves almacena información acerca de la combinación y dejar información para una conferencia. Cada conferencia se representa en esta vista mediante un registro escrito cada vez que un usuario se une y abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de la conferencia. Se utiliza junto con SessionIdSeq para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la instancia de la conferencia. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario cuya información de combinación o abandonarlo conferencia fue capturada.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario cuya información de combinación o abandonarlo conferencia fue capturada. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario cuya información de combinación o abandonarlo conferencia fue capturada. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario cuya información de combinación o abandonarlo conferencia fue capturada.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario cuya información de combinación o abandonarlo conferencia fue capturada.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente utilizado el usuario cuya información de combinación o abandonarlo conferencia fue capturada. Para obtener más detalles, vea [tabla de UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente utilizado por el usuario cuya información de combinación o abandonarlo conferencia fue capturada.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que indica si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un usuario inicia sesión en varios equipos o dispositivos al mismo tiempo, UserInstance se utiliza para identificar de forma exclusiva la combinación usuario/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo SIP de la sesión. El formato es: diálogo de etiqueta; a la etiqueta.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Tiempo que el usuario se unió a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Tiempo que el usuario abandonó la conferencia.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Función del usuario en la conferencia como moderador o asistente.  <br/> |
   

