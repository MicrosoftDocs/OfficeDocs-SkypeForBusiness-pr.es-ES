---
title: Tabla ErrorReport en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La tabla ErrorReport almacena información sobre los errores que se han producido. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.
ms.openlocfilehash: de103c61f74b50297f9c012ae7f4c6e1586e87d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815228"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabla ErrorReport en Skype empresarial Server 2015
 
La tabla ErrorReport almacena información sobre los errores que se han producido. Cada registro es una aparición de error. Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que se produjo el error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar el informe de errores. Se usa en conjunción con **ErrorTime** para identificar de manera exclusiva un informe de errores. <br/> |
|**ErrorId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR único del tipo de error. Para obtener más información, consulte la [tabla ErrorDef en Skype empresarial Server 2015](errordef.md) . <br/> |
|**FromUserId** <br/> |int  <br/> |Extranjero  <br/> |Usuario que originó la solicitud que causó el error. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**ToUserId** <br/> |int  <br/> |Extranjero  <br/> |Usuario de destino de la solicitud que causó el error. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Extranjero  <br/> |URI de conferencia relacionado con el error. Para obtener más información, consulte la [tabla ConferenceUris en Skype empresarial Server 2015](conferenceuris.md) . Normalmente, si ConferenceUriId no es null, FromUserId o ToUserId será null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Extranjero  <br/> |Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SourceId** <br/> |int  <br/> |Extranjero  <br/> |Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor). Para obtener más información, consulte la [tabla servidores](servers.md) . <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Extranjero  <br/> |Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor). Para obtener más información, consulte la [tabla de aplicaciones en Skype empresarial Server 2015](application.md) . <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagen  <br/> | <br/> |Más información sobre el error.  <br/> Estos datos se pueden convertir a formato de texto con esta sintaxis:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Extranjero  <br/> |La versión de cliente del extremo que envía el informe de errores. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.  <br/> |
|**Fdisableautoindexingonschemaupdate** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**TelemetryId** <br/> |Identificador  <br/> ||Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Extranjero  <br/> |Representa el nombre de dominio completo del servidor que ha generado el informe de errores.  <br/> |
|**PoolId** <br/> |int  <br/> |Extranjero  <br/> |Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

