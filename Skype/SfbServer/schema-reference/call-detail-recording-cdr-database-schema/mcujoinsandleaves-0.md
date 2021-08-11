---
title: Vista McuJoinsAndLeaves
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vista McuJoinsAndLeaves almacena información sobre el momento en que los usuarios se unen a un servidor de conferencia o lo abandonan. Cada uno de los registros de esta vista contiene detalles de llamada sobre una combinación del servidor de conferencia y de la información sobre la entrada o la salida del mismo. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 50213655ad1dc48e85015d47ac4bd5bb450e05559556e0d6b4123dc2c9c32d69
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318723"
---
# <a name="mcujoinsandleaves-view"></a>Vista McuJoinsAndLeaves
 
La vista McuJoinsAndLeaves almacena información sobre el momento en que los usuarios se unen a un servidor de conferencia o lo abandonan. Cada uno de los registros de esta vista contiene detalles de llamada sobre una combinación del servidor de conferencia y de la información sobre la entrada o la salida del mismo. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |URI del servidor de conferencia al que se conectó el usuario.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |URI del servidor de conferencia al que se conectó el usuario. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario del que se capturó la información de entrada/salida del servidor de conferencia. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.  <br/> |
|**UserClientType** <br/> |Entero  <br/> |Cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia. Consulta la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.  <br/> |
|**McuUserInstance** <br/> |Entero  <br/> |Identificación única de la combinación usuario/dispositivo para los usuarios con una sesión iniciada en varios dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que representa si el usuario es interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |Entero  <br/> |Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora a la que el usuario se unió al servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora a la que el usuario abandonó el servidor de conferencia.  <br/> |
   

