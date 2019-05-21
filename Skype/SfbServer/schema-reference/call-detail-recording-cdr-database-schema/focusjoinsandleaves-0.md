---
title: Vista FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vista FocusJoinsAndLeaves almacena información acerca de la Unión y la información de salida de una conferencia. Cada conferencia se representa en esta vista por un registro que se escribe cada vez que un usuario se une y sale de la Conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: f739ae390b636913d96b49dd516d2618c72515e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296220"
---
# <a name="focusjoinsandleaves-view"></a>Vista FocusJoinsAndLeaves
 
La vista FocusJoinsAndLeaves almacena información acerca de la Unión y la información de salida de una conferencia. Cada conferencia se representa en esta vista por un registro que se escribe cada vez que un usuario se une y sale de la Conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la instancia de la Conferencia. Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI del usuario en el que se capturó la información de unión o salida de la Conferencia.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario cuya información de unión o salida de conferencia se capturó. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario cuya información de unión o salida de conferencia fue capturada. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**UserEndpointId** <br/> |identificador  <br/> |Identificador único del usuario cuya información de unión o salida de conferencia se capturó.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usada por el usuario cuya información de unión o salida de conferencia ha sido capturada.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado por el usuario cuya información de unión o salida de conferencia fue capturada. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nombre de la categoría del cliente usada por el usuario cuya información de unión o salida de conferencia fue capturada.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que representa si el usuario es un usuario interno o no.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un usuario ha iniciado sesión en varios equipos o dispositivos al mismo tiempo, UserInstance se usa para identificar de forma inequívoca la combinación de usuario y dispositivo.  <br/> |
|**DialogId** <br/> |VARCHAR (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión. El formato es: diálogo; de-etiqueta; to-TAG.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |El momento en que el usuario se unió a la Conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Tiempo que el usuario abandonó la Conferencia.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Función del usuario en la Conferencia, como moderador o asistente.  <br/> |
   

