---
title: Tabla SessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa una sesión de peer-to-peer, que puede ser una llamada de teléfono VoIP VoIP, sesión de mensajería instantánea de dos partes u otro tipo de sesión. Puede realizar una combinación de tablas con la tabla de medios para encontrar los detalles de cada uno de los medios implicados en esta sesión.
ms.openlocfilehash: 9c6cbe0b69871aa4876777b235d14f8a7ced0e15
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-table"></a>Tabla SessionDetails
 
Cada registro representa una sesión de peer-to-peer, que puede ser una llamada de teléfono VoIP VoIP, sesión de mensajería instantánea de dos partes u otro tipo de sesión. Puede realizar una combinación de tablas con la [tabla de medios](media.md) para encontrar los detalles de cada uno de los medios implicados en esta sesión.
  
Tenga en cuenta que los campos IsUser2IntegratedWithDeskPhone y el IsUser1IntegratedWithDeskPhone se han quitado de la tabla SessionDetails en Skype para Business Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva un session.*, vea la [tabla en Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||Un GUID para correlacionar múltiples sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de ID para identificar el cuadro de diálogo que se ha reemplazado por la sesión actual. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **ReplacesDialogIdTime** para identificar una sesión que es reemplazada por esta sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**User1Id** <br/> |int  <br/> |Externa  <br/> |ID. de un usuario en la sesión. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**User2Id** <br/> |int  <br/> |Externa  <br/> |Id. del otro usuario en la sesión. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo utilizado por el primer usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo utilizado por el segundo usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Externa  <br/> |Solicitar el original para el URI de SIP del usuario. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Externa  <br/> |Id. del usuario que inició la sesión. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica el identificador del usuario de quién es el llamador en nombre. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |Id. del usuario por el que se conoce la llamada. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Id. del servidor front-end utilizado para esta sesión. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Id. de la agrupación en la que fue capturada la sesión. Consulte la [tabla de grupos](pools.md) para obtener más información. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Externa  <br/> |Tipo de contenido utilizado en la sesión. Consulte la [tabla de tipos de contenido en Skype para Business Server 2015](contenttypes.md) para obtener más información. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente utilizada por usuario1. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente utilizada por el usuario2. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor de borde utilizado por usuario1. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor de borde utilizado por el usuario2. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Si Usuario1 inicia sesión desde interna o no.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Si usuario2 ha iniciado sesión desde interna o no.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||La hora de la primera solicitud de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información). Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||La hora de la respuesta al primer mensaje de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta SIP a la invitación de sesión. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID. de diagnóstico capturado de encabezado SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Externa  <br/> |Llame a prioridad. Consulte la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md) para obtener más información. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Número de mensajes enviados por el Usuario1 durante la sesión.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Número de mensajes enviados por el usuario2 durante la sesión.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Tiempo al final de la sesión.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un bit que indica el tipo de medio de esta sesión. Aparecen las definiciones de los tipos:  <br/> 1 - IM  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - AUDIO  <br/> 32 - VÍDEO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de Usuario1. Se enumeran las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de usuario2. Se enumeran las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:  <br/> 0 x 01 - reintenta la sesión  <br/> 0 x 02 - una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Procesado** <br/> |bit  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones SessionIdSeq tendrá el valor 1. Si iniciar varias sesiones al mismo tiempo, la SessionIdSeq de uno será 1, otro 2 y así sucesivamente.
  

