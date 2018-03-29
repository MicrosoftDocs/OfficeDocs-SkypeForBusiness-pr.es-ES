---
title: Tabla de ErrorReport en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La tabla de ErrorReport almacena información sobre los errores que se han producido. Cada registro es una aparición del error. Los errores son capturados por el agente en el servidor front-end CDR o enviados desde el cliente.
ms.openlocfilehash: 80ae8cb9fb4bea586ac31456fc396856e5263a34
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabla de ErrorReport en Skype para Business Server 2015
 
La tabla de ErrorReport almacena información sobre los errores que se han producido. Cada registro es una aparición del error. Los errores son capturados por el agente en el servidor front-end CDR o enviados desde el cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que ocurrió el error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de ID para identificar el informe de errores. Se utiliza junto con **ErrorTime** para identificar un informe de errores. <br/> |
|**Identificador del error** <br/> |int  <br/> |Externa  <br/> |Identificador exclusivo del tipo de error. Consulte la [tabla ErrorDef en Skype para Business Server 2015](errordef.md) para obtener más información. <br/> |
|**FromUserId** <br/> |int  <br/> |Externa  <br/> |Usuario que originó la solicitud que provocó el error. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**ToUserId** <br/> |int  <br/> |Externa  <br/> |Usuario de destino para la solicitud que provocó el error. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferencia de URI relacionado con el error. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Normalmente, si ConferenceUriId no es null, a continuación, FromUserId o ToUserId es nulo. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se envía desde un componente de servidor). Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se envía desde un componente de servidor). Consulte la [tabla de aplicación de Skype para Business Server 2015](application.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagen  <br/> | <br/> |Más información sobre el error.  <br/> Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |La versión de cliente de extremo que envía el informe de errores. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||El informe de errores es capturado por el agente en el servidor front-end CDR o enviado por el cliente.  <br/> |
|**Indicador** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único correlacionando la información de tiempo de participación de los diferentes componentes implicados en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) necesario para que un determinado componente para unirse a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Representa el nombre de dominio completo del servidor que genera el informe de errores.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Representa el nombre de dominio completo del grupo donde se generó el informe de errores.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

