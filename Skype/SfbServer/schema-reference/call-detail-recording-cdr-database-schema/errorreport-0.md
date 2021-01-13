---
title: Vista ErrorReport
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vista ErrorReport almacena información sobre los errores que se notifican. Cada registro representa la aparición de un error. Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: e00e2bddaea34be6b09bc211991539ad6123603e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821720"
---
# <a name="errorreport-view"></a>Vista ErrorReport
 
La vista ErrorReport almacena información sobre los errores que se notifican. Cada registro representa la aparición de un error. Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.  <br/> |
|**ErrorReportSeq** <br/> |entero  <br/> |Número para identificar el error. Se usa en combinación con ErrorTime para identificar el error de forma exclusiva.  <br/> |
|**MsDiagId** <br/> |entero  <br/> |Identificador de diagnóstico del informe de errores.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha originado el error.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha originado el error. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que ha originado el error. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario destinatario del informe de errores.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario destinatario del informe de errores. Para más información, consulte la tabla UriTypes.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario destinatario del informe de errores. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia destinataria del informe de errores.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la conferencia destinataria del informe de errores. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de la sesión que originó el informe de errores. Se usa de forma conjunta con SessionIdseq para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Número para identificar la solicitud de sesión que originó el informe de errores. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificador de diálogo SIP que originó el error. El formato es:  <br/> dialog;from-tag;to-tag  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente que usa el usuario que originó el error.  <br/> |
|**ClientType** <br/> |entero  <br/> |Cliente que usa el usuario que originó el error. Vea la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de categoría del cliente que usa el usuario que originó el error.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**ResponseCode** <br/> |entero  <br/> |Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Tipo de solicitud que ha generado errores.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Tipo de contenido de la solicitud que ha generado errores.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sesión. Consulte la [tabla CallType en Skype Empresarial Server 2015](calltype.md) para obtener más información. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.  <br/> |
|**SetupTime** <br/> |entero  <br/> |Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica si el informe de errores fue capturado por el agente del CDR que se ejecuta en el servidor front-end o si lo envió el cliente.  <br/> |
|**Flag** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Más información sobre el error.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nombre de dominio completo del servidor front-end que envió el informe.  <br/> |
|**Grupo** <br/> |nvarchar  <br/> |Nombre de dominio completo del grupo que contiene el servidor front-end que envió el informe.  <br/> |
   

