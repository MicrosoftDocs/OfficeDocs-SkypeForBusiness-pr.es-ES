---
title: Tabla ConferenceSessionDetails en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa una sesión de conferencia, que podría ser la sesión con el foco o la sesión con un servidor de conferencia específica.
ms.openlocfilehash: 72f2eb11c79348ad72815be7acfd337a40d288af
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabla ConferenceSessionDetails en Skype para Business Server 2015
 
Cada registro representa una sesión de conferencia, que podría ser la sesión con el foco o la sesión con un servidor de conferencia específica.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Fecha y hora  <br/> |Principal, externa  <br/> |Tiempo de solicitud de sesión; se utiliza junto con **SessionIdSeq** para identificar una sesión de conferencia. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión de conferencia. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferencia de foco URI relacionados con esta sesión. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Este identificador URI es una conferencia de foco URI. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificador que distingue entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferencia de Conferencing server URI relacionados con esta sesión. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Este identificador URI es la conferencia basada en servidor de conferencia URI. Para la sesiones de la conferencia de foco, esta columna será null. <br/> |
|**ID de usuario** <br/> |int  <br/> |Externa  <br/> |ID. de un usuario en la sesión de conferencia. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID para identificar la instancia del extremo. Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, a continuación, cada máquina tendrá un identificador de extremo diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica el identificador del usuario de quién es el llamador en nombre. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |Id. del usuario por el que se conoce la llamada. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente utilizada por el usuario de la conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente utilizada por el servidor de conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de ID para identificar el cuadro de diálogo que se ha reemplazado por la sesión actual. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **ReplacesDialogIdTime** para identificar una sesión que es reemplazada por esta sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica si la sesión iniciada por el servidor de conferencias.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica si finalizó la sesión en el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si usuario ha iniciado sesión desde interna o no.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta de protocolo de inicio (SIP) de sesión a la invitación de sesión. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID. de diagnóstico capturado de encabezado SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Id. del servidor front-end utilizado para esta sesión. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Id. de la agrupación en la que fue capturada la sesión. Consulte la [tabla de grupos](pools.md) para obtener más información. <br/> |
|**MediationServerId** <br/> |int  <br/> |Externa  <br/> |Está utilizando el servidor de mediación de la llamada. Consulte la [tabla de MediationServers](mediationservers.md) para obtener más información. <br/> |
|**GatewayId** <br/> |int  <br/> |Externa  <br/> |Utiliza la puerta de enlace la llamada. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |Está utilizando el servidor perimetral de la llamada. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de contenido utilizado en la sesión. Consulte la [tabla de tipos de contenido en Skype para Business Server 2015](contenttypes.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||La hora de la primera solicitud de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la primera respuesta SIP. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||El tiempo cuando se termina la sesión.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externa  <br/> |Contiene el valor del tipo de URI MCU de la [tabla UriTypes](uritypes.md). Este campo se utiliza para mejorar el rendimiento de las consultas.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Un bit establecido indica los atributos de usuario. Se enumeran las siguientes definiciones de atributo: <br/>  Integrado con el teléfono de escritorio - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Un bit establecido indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo: <br/>  Sesión reintentado - 1 <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones SessionIdSeq tendrá el valor 1. Si iniciar varias sesiones al mismo tiempo, la SessionIdSeq de uno será 1, otro 2 y así sucesivamente.
  

