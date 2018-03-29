---
title: Vista de ErrorReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vista ErrorReport almacena información acerca de los errores notificados. Cada registro es una aparición del error. Los errores son capturados por el agente en el servidor front-end CDR o enviados desde el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b1815d4420b5768b065a5695ea09174ecff91912
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-view"></a>Vista de ErrorReport
 
La vista ErrorReport almacena información acerca de los errores notificados. Cada registro es una aparición del error. Los errores son capturados por el agente en el servidor front-end CDR o enviados desde el cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Se ha producido el momento del error. Se utiliza junto con ErrorReportSeq para identificar un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de ID para identificar el error. Se utiliza junto con ErrorTime para identificar un error.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Id. de diagnóstico para el informe de errores.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que originó el error.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que originó el error. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que originó el error. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario que era el destino del informe de error.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que el destino del informe de error. Consulte la tabla UriTypes para obtener más información.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario que el destino del informe de error. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia que era el destino del informe de error.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo URI de la conferencia que era el destino del informe de error. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Tiempo de solicitud de sesión que se originó el informe de errores. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la solicitud de sesión que se originó el informe de errores. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Cuadro de diálogo ID de sesión que originó el error del SIP. El formato es:  <br/> diálogo de etiqueta; para etiqueta  <br/> Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:  <br/> conversión de tipos (cast (ExternalID no como varbinary(max)) como varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario que originó el error.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Cliente utilizado por el usuario que originó el error. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente utilizado por el usuario que originó el error.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que se originó el error (si se ha enviado desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que originó el error (si se ha enviado desde un componente de servidor).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta a la sesión del mensaje SIP que contiene el informe de errores de SIP.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Tipo de solicitud que falló.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Tipo de contenido de la solicitud que falló.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo de sesión. Consulte la [tabla de CallType en Skype para Business Server 2015](calltype.md) para obtener más información. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único correlacionando la información de tiempo de participación de los diferentes componentes implicados en una conferencia.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un determinado componente para unirse a una conferencia.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica si el informe de errores se ha capturado por el agente en el servidor Front-End CDR o enviados por el cliente.  <br/> |
|**Indicador** <br/> |smallint  <br/> |Reservado para uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Información adicional sobre el error.  <br/> |
|**Front-end** <br/> |nvarchar  <br/> |Nombre de dominio completo del servidor Front-End que presentó el informe.  <br/> |
|**Grupo de servidores** <br/> |nvarchar  <br/> |Nombre de dominio del grupo que contiene el servidor Front-End que envió el informe completo.  <br/> |
   

