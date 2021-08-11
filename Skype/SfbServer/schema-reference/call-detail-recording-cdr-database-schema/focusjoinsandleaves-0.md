---
title: Vista FocusJoinsAndLeaves
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia. Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 12bfac794378a27c612a5afa06d63c57ba23bbcdce3ea1bd7e928a663d99fd3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278368"
---
# <a name="focusjoinsandleaves-view"></a>Vista FocusJoinsAndLeaves
 
La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia. Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario del que se ha capturado la información de incorporación/abandono.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Escriba la URI del usuario del que se ha capturado la información de incorporación/abandono. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario del que se ha capturado la información de incorporación/abandono. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario del que se ha capturado la información de incorporación/abandono.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usada por el usuario del que se ha capturado la información de incorporación/abandono.  <br/> |
|**UserClientType** <br/> |Entero  <br/> |Cliente que ha usado el usuario del que se ha capturado la información de incorporación/abandono. Consulte [la tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario del que se ha capturado la información de incorporación/abandono.  <br/> |
|**FocusUserInstance** <br/> |Entero  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que representa si el usuario es interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |Entero  <br/> |Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora a la que el usuario se incorporó a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora a la que el usuario abandonó la conferencia.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rol del usuario en la conferencia, como moderador o asistente.  <br/> |
   

