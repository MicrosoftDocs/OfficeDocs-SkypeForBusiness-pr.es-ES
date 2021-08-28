---
title: Tabla ErrorReport en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La tabla ErrorReport almacena información sobre los errores que se han producido. Cada registro representa la aparición de un error. Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.
ms.openlocfilehash: d2fccd6f1f99884e9d4412cb9814f24d581248a5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634184"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabla ErrorReport en Skype Empresarial Server 2015
 
La tabla ErrorReport almacena información sobre los errores que se han producido. Cada registro representa la aparición de un error. Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal  <br/> |Fecha y hora en que se produjo el error.  <br/> |
|**ErrorReportSeq** <br/> |Entero  <br/> |Principal  <br/> |Número de identificador para identificar el informe de errores. Se usa junto con **ErrorTime para** identificar de forma única un informe de errores. <br/> |
|**ErrorId** <br/> |Entero  <br/> |Externo  <br/> |Identificador único del tipo de error. Vea la [tabla ErrorDef en Skype Empresarial Server 2015](errordef.md) para obtener más información. <br/> |
|**FromUserId** <br/> |Entero  <br/> |Externo  <br/> |Usuario que originó la solicitud que provocó el error. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ToUserId** <br/> |Entero  <br/> |Externo  <br/> |Usuario de destino de la solicitud que provocó el error. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ConferenceUriId** <br/> |Entero  <br/> |Externo  <br/> |URI de conferencia relacionado con el error. Vea la [tabla ConferenceUris de Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. Normalmente, si ConferenceUriId no es null, FromUserId o ToUserId serán null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Externo  <br/> |Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Externo  <br/> |Número con el que se identifica la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**Proveniente** <br/> |Entero  <br/> |Externo  <br/> |Servidor que envió el informe de error (si el informe se envía desde un componente de servidor). Vea la [tabla Servidores para](servers.md) obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |Entero  <br/> |Externo  <br/> |Servidor que envió el informe de error (si el informe se envía desde un componente de servidor). Vea la [tabla Application en Skype Empresarial Server 2015](application.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |imagen  <br/> | <br/> |Más información sobre el error.  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |Entero  <br/> |Externo  <br/> |La versión de cliente del extremo que envía el informe de errores. Vea la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Es el informe de error capturado por el agente de CDR que se ejecuta en el servidor front-end o enviado por el cliente.  <br/> |
|**Flag** <br/> |smallint  <br/> ||Reservado para uso futuro.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |Entero  <br/> ||Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |Entero  <br/> |Externo  <br/> |Representa el nombre de dominio completo del servidor que generó el informe de errores.  <br/> |
|**PoolId** <br/> |Entero  <br/> |Externo  <br/> |Representa el nombre de dominio completo del grupo donde se generó el informe de errores.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

