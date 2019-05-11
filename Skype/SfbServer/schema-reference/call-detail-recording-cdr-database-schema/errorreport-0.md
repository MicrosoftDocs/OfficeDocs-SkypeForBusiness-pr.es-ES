---
title: Vista ErrorReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vista ErrorReport almacena información acerca de errores notificados. Cada registro es una ocurrencia de error. Los errores son capturado por el agente de CDR que se ejecuta en el servidor front-end o enviados desde el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d188972cfa806b162e8da251af045cc10c84b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901104"
---
# <a name="errorreport-view"></a>Vista ErrorReport
 
La vista ErrorReport almacena información acerca de errores notificados. Cada registro es una ocurrencia de error. Los errores son capturado por el agente de CDR que se ejecuta en el servidor front-end o enviados desde el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora de error se ha producido. Se utiliza junto con ErrorReportSeq para identificar de forma única un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificador para identificar el error. Se utiliza junto con ErrorTime para identificar de forma única un error.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Identificador de diagnóstico para el informe de errores.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que originó el error.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que originó el error. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que originó el error. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario que era el destino del informe de errores.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de usuario de destino del informe de errores. Consulte la tabla UriTypes para obtener más información.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que de destino del informe de errores. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia que era el destino del informe de errores.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la conferencia que era el destino del informe de errores. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión que generó el informe de errores. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la solicitud de sesión que generó el informe de errores. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificador del cuadro de diálogo SIP de sesión que originó el error. El formato es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> Estos datos pueden convertirse a formato de texto con esta sintaxis:  <br/> CAST (cast (ExternalId as varbinary como varchar  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que originó el error.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Cliente usado por el usuario que originó el error. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario que originó el error.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de aplicación que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta a la sesión del mensaje SIP que contiene el informe de errores de SIP.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Tipo de solicitud que ha fallado.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Tipo de contenido de la solicitud que ha fallado.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sesión. Vea la [tabla CallType en Skype para Business Server 2015](calltype.md) para obtener más información. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único que correlaciona la información de hora para los diferentes componentes que participan en una conferencia.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un componente específico para unirse a una conferencia.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica si el informe de errores se ha capturado por el agente de CDR que se ejecuta en el servidor Front-End o enviado por el cliente.  <br/> |
|**Marca** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Información adicional sobre el error.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nombre de dominio completo del servidor Front-End que han enviado el informe.  <br/> |
|**Grupo** <br/> |nvarchar  <br/> |Nombre de dominio del grupo de servidores que contiene el servidor Front-End que han enviado el informe completo.  <br/> |
   

