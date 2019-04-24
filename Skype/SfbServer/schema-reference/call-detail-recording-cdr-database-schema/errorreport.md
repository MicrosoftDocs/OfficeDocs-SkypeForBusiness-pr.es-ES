---
title: Tabla ErrorReport en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: En la tabla ErrorReport almacena información acerca de los errores que se han producido. Cada registro es una ocurrencia de error. Los errores son capturado por el agente de CDR que se ejecuta en el servidor front-end o enviados desde el cliente.
ms.openlocfilehash: 99dcdc7aa78b20f555f94614ba94c80103b56211
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213133"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabla ErrorReport en Skype para Business Server 2015
 
En la tabla ErrorReport almacena información acerca de los errores que se han producido. Cada registro es una ocurrencia de error. Los errores son capturado por el agente de CDR que se ejecuta en el servidor front-end o enviados desde el cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que se produjo el error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificador para identificar el informe de errores. Se utiliza junto con **ErrorTime** para identificar de forma única un informe de errores. <br/> |
|**Identificador del error** <br/> |int  <br/> |Externa  <br/> |Identificador único del tipo de error. Consulte la [tabla ErrorDef en Skype para Business Server 2015](errordef.md) para obtener más información. <br/> |
|**FromUserId** <br/> |int  <br/> |Externa  <br/> |Usuario que ha originado la solicitud que provocó el error. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**ToUserId** <br/> |int  <br/> |Externa  <br/> |Usuario de destino para la solicitud que provocó el error. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI de conferencia relacionada con el error. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Normalmente, si ConferenceUriId no es nulo, a continuación, FromUserId o ToUserId será null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se envía desde un componente de servidor). Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se envía desde un componente de servidor). Consulte la [tabla de la aplicación en Skype para Business Server 2015](application.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagen  <br/> | <br/> |Obtener más información sobre el error.  <br/> Estos datos pueden convertirse a formato de texto con esta sintaxis:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externa  <br/> |La versión de cliente de extremo que envía el informe de errores. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||El informe de errores es capturado por el agente de CDR que se ejecuta en el servidor front-end o enviado por el cliente.  <br/> |
|**Marca** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona la información de hora para los diferentes componentes que participan en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) necesario para que un componente específico para unirse a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Representa el nombre de dominio completo del servidor que generó el informe de errores.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Representa el nombre de dominio completo del grupo de servidores donde se generó el informe de errores.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

