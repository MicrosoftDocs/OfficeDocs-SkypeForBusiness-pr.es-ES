---
title: Vista FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vista FocusJoinsAndLeaves almacena información acerca de la combinación y deje la información de una conferencia. Cada conferencia se representa en esta vista por un objeto record escrito cada vez que un usuario se une a y abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4fa6a2ec043c5f9746a14d5214be9ad531159cd7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213679"
---
# <a name="focusjoinsandleaves-view"></a>Vista FocusJoinsAndLeaves
 
La vista FocusJoinsAndLeaves almacena información acerca de la combinación y deje la información de una conferencia. Cada conferencia se representa en esta vista por un objeto record escrito cada vez que un usuario se une a y abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la instancia de conferencia. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario incorporación/abandono información que se ha capturado.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario incorporación/abandono información que se ha capturado. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario incorporación/abandono información que se ha capturado. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario incorporación/abandono información que se ha capturado.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario incorporación/abandono información que se ha capturado.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado por el usuario incorporación/abandono información que se ha capturado. Para obtener más información, consulte [tabla UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario incorporación/abandono información que se ha capturado.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que representa si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador del cuadro de diálogo SIP de la sesión. El formato es: cuadro de diálogo; de etiqueta; para la etiqueta.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Tiempo que el usuario se unió a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora en que el usuario abandonó la conferencia.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rol del usuario en la conferencia, por ejemplo moderador o asistente.  <br/> |
   

