---
title: Tabla SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa una sesión de punto a punto, que puede ser una llamada de teléfono VoIP-VoIP, una sesión de mi de dos partes u otro tipo de sesión. Puede realizar una combinación de tabla con la tabla multimedia para buscar los detalles de cada elemento multimedia implicado en esta sesión.
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295807"
---
# <a name="sessiondetails-table"></a>Tabla SessionDetails
 
Cada registro representa una sesión de punto a punto, que puede ser una llamada de teléfono VoIP-VoIP, una sesión de mi de dos partes u otro tipo de sesión. Puede realizar una combinación de tabla con la [tabla multimedia](media.md) para buscar los detalles de cada elemento multimedia implicado en esta sesión.
  
Observe que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails que se usa en Skype empresarial Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa junto con **SessionIdTime** para identificar una sesión de forma única. * Consulte la [tabla de cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**CorrelationId** <br/> |identificador  <br/> ||Un GUID para correlacionar varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Extranjero  <br/> |Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Extranjero  <br/> |Número de identificación para identificar la sesión. Se usa junto con **ReplacesDialogIdTime** para identificar de forma única una sesión que se reemplaza por esta sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**User1Id** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR de un usuario de la sesión. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**User2Id** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del otro usuario de la sesión. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**User1EndpointId** <br/> |Identificador  <br/> ||GUID que identifica el extremo utilizado por el primer usuario de la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |Identificador  <br/> ||GUID que identifica el extremo usado por el segundo usuario de la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Extranjero  <br/> |El URI del usuario original para la solicitud SIP. para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**SessionStartedById** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del usuario que inició la sesión. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Extranjero  <br/> |Indica el identificador del usuario de la persona que llama en nombre. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del usuario al que hace referencia la llamada. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**ServerId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del servidor front-end usado para esta sesión. Para obtener más información, consulte la [tabla servidores](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la [tabla grupos](pools.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Extranjero  <br/> |Tipo de contenido usado en la sesión. Para obtener más información, consulte la [tabla contentTypes en Skype empresarial Server 2015](contenttypes.md) . <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Extranjero  <br/> |Versión de cliente usada por el usuario1. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Extranjero  <br/> |Versión de cliente usada por usuario2. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Extranjero  <br/> |Servidor perimetral usado por el usuario1. Para obtener más información, consulte la [tabla EdgeServers en Skype empresarial Server 2015](edgeservers.md) . <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Extranjero  <br/> |Servidor perimetral usado por usuario2. Para obtener más información, consulte la [tabla EdgeServers en Skype empresarial Server 2015](edgeservers.md) . <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Si user1 está conectado desde interno o no.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Si usuario2 está conectado desde interno o no.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||La hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información). Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||La hora de la respuesta al primer mensaje de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Extranjero  <br/> |Prioridad de la llamada. Para obtener más información, consulte la [tabla CallPriorities en Skype empresarial Server 2015](callpriorities.md) . <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Número de mensajes enviados por el usuario1 durante la sesión.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Número de mensajes enviados por usuario2 durante la sesión.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora de finalización de la sesión.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un conjunto de bits que indica el tipo de medio de esta sesión. En la lista se muestran las definiciones de los tipos:  <br/> 1-MI  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-AUDIO  <br/> 32-VIDEO  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Un conjunto de bits que indica los atributos del Usuario1. Se muestran las siguientes definiciones de atributos:  <br/> 0x01: integrado con un teléfono de escritorio  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Un conjunto de bits que indica los atributos de usuario2. Se muestran las siguientes definiciones de atributos:  <br/> 0x01: integrado con un teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Un conjunto de bits que indica los atributos de la llamada. Se muestran las siguientes definiciones de atributos:  <br/> 0x01-reintento de sesión  <br/> 0x02: una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Procesar** <br/> |bit  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.
  

