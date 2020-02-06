---
title: Vista ErrorReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vista ErrorReport almacena información sobre los errores notificados. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: d51b085d5dabb8a6ae0dc367b23dd23a1702174e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815248"
---
# <a name="errorreport-view"></a>Vista ErrorReport
 
La vista ErrorReport almacena información sobre los errores notificados. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora de error. Se usa junto con ErrorReportSeq para identificar de forma única un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificación para identificar el error. Se usa junto con ErrorTime para identificar de forma única un error.  <br/> |
|**MsDiagId** <br/> |int  <br/> |IDENTIFICADOR de diagnóstico del informe de errores.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que originó el error.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que originó el error. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que originó el error. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**ToUr** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que era el destino del informe de errores.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se dirige al informe de errores. Para obtener más información, consulte la tabla UriTypes.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que se dirige al informe de errores. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conferencia que era el destino del informe de errores.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la Conferencia que era el destino del informe de errores. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión que originó el informe de errores. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la solicitud de sesión que originó el informe de errores. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |IDENTIFICADOR del cuadro de diálogo SIP de la sesión que originó el error. El formato es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> Estos datos se pueden convertir a formato de texto con esta sintaxis:  <br/> CAST (Cast) (ExternalId as varbinary (Max)) as VARCHAR (Max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente utilizada por el usuario que originó el error.  <br/> |
|**Tipocliente** <br/> |int  <br/> |Cliente usado por el usuario que originó el error. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Nombre de la categoría del cliente que ha usado el usuario que originó el error.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.  <br/> |
|**RequestType** <br/> |VARCHAR (Max)  <br/> |Tipo de solicitud en la que se produjo un error.  <br/> |
|**ContentType** <br/> |VARCHAR (Max)  <br/> |Tipo de contenido de la solicitud en la que se produjo un error.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sesión. Para obtener más información, consulte la [tabla CallType en Skype empresarial Server 2015](calltype.md) . <br/> |
|**TelemetryId** <br/> |identificador  <br/> |Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica si el informe de errores fue capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.  <br/> |
|**Fdisableautoindexingonschemaupdate** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |VARCHAR (Max)  <br/> |Información adicional sobre el error.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nombre de dominio completo del servidor front-end que ha enviado el informe.  <br/> |
|**Grupo** <br/> |nvarchar  <br/> |Nombre de dominio completo del grupo que contiene el servidor front-end que ha enviado el informe.  <br/> |
   

