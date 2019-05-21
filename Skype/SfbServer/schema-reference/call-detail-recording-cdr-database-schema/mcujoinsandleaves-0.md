---
title: Vista McuJoinsAndLeaves
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vista McuJoinsAndLeaves almacena información sobre los usuarios que se unen y salen de la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de la llamada sobre una combinación de una Unión de usuario o el servidor abandonar y Conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 9d5617449e5b12c13d855c1a93b39490e2177f0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296080"
---
# <a name="mcujoinsandleaves-view"></a>Vista McuJoinsAndLeaves
 
La vista McuJoinsAndLeaves almacena información sobre los usuarios que se unen y salen de la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de la llamada sobre una combinación de una Unión de usuario o el servidor abandonar y Conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la instancia de la Conferencia. Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencia al que se conectó el usuario.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |El URI del servidor de conferencia al que se conectó el usuario. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |El URI del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |El tipo de URI del usuario en el que se capturó la información de Unión/salida del servidor de conferencias. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La versión de cliente utilizada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.  <br/> |
|**UserClientType** <br/> |int  <br/> |El cliente usado por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |El nombre de la categoría del cliente usada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica de forma única la combinación de usuarios y dispositivos para los usuarios que tienen iniciada sesión simultáneamente en varios dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que representa si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |VARCHAR (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión. El formato es: diálogo; de-etiqueta; to-TAG.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Momento en que el usuario se unió al servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |El momento en que el usuario abandonó el servidor de conferencia.  <br/> |
   

