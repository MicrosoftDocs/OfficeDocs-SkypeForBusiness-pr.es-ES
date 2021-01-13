---
title: Tabla SessionDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión. Puedes realizar una combinación de tabla con la tabla Multimedia para encontrar los detalles de cada medio implicado en esta sesión.
ms.openlocfilehash: d2b213f6f71ceae84a0625774168bc78c8d9f17f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809940"
---
# <a name="sessiondetails-table"></a>Tabla SessionDetails
 
Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión. Puedes realizar una combinación de tabla con la [tabla Multimedia](media.md) para encontrar los detalles de cada medio implicado en esta sesión.
  
Tenga en cuenta que los campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone se han eliminado de la tabla SessionDetails usada en Skype Empresarial Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa junto con **SessionIdTime** para identificar de forma única una sesión.* Vea la tabla Cuadros de diálogo en [Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||GUID con el que se correlacionan varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externo  <br/> |Número con el que se identifica el diálogo que se reemplazó por la sesión actual. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |entero  <br/> |Externo  <br/> |Número con el que se identifica la sesión. Se usa junto con **ReplacesDialogIdTime** para identificar de manera exclusiva una sesión que se reemplazó por esta sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**User1Id** <br/> |entero  <br/> |Externo  <br/> |Identificador de un usuario de la sesión. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**User2Id** <br/> |entero  <br/> |Externo  <br/> |Identificador de otro usuario de la sesión. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo que utilizó el primer usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo que utilizó el segundo usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |entero  <br/> |Externo  <br/> |URI de destinatario original en la solicitud SIP. vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**SessionStartedById** <br/> |entero  <br/> |Externo  <br/> |Identificador del usuario que inició la sesión. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**OnBehalfOfId** <br/> |entero  <br/> |Externo  <br/> |Señala el identificador de usuario en cuyo nombre llama el autor de la llamada. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |entero  <br/> |Externo  <br/> |Identificador del usuario por el que se hace referencia a la sesión. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ServerId** <br/> |entero  <br/> |Externo  <br/> |Identificador del servidor front-end usado en esta sesión. Vea la [tabla Servidores para](servers.md) obtener más información. <br/> |
|**PoolId** <br/> |entero  <br/> |Externo  <br/> |Identificador del grupo en el que se capturó la sesión. Vea la tabla [Grupos de](pools.md) servidores para obtener más información. <br/> |
|**ContentTypeID** <br/> |entero  <br/> |Externo  <br/> |Tipo de contenido empleado en la sesión. Consulte la [tabla ContentTypes en Skype Empresarial Server 2015](contenttypes.md) para obtener más información. <br/> |
|**User1ClientVerId** <br/> |entero  <br/> |Externo  <br/> |Versión de cliente usada por el usuario 1. Consulte la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**User2ClientVerId** <br/> |entero  <br/> |Externo  <br/> |Versión de cliente usada por el usuario 2. Consulte la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**User1EdgeServerid** <br/> |entero  <br/> |Externo  <br/> |Servidor perimetral usado por el usuario 1. Consulte la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**User2EdgeServerid** <br/> |entero  <br/> |Externo  <br/> |Servidor perimetral usado por el usuario 2. Consulte la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Indica si el usuario 1 ha iniciado sesión de manera interna o no.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Indica si el usuario 2 ha iniciado sesión de manera interna o no.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO). Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de respuesta al primer mensaje INVITE. Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |entero  <br/> ||Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |entero  <br/> ||Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**CallPriority** <br/> |entero  <br/> |Externo  <br/> |Prioridad de la llamada. Consulte la [tabla CallPriorities en Skype Empresarial Server 2015](callpriorities.md) para obtener más información. <br/> |
|**User1MessageCount** <br/> |entero  <br/> ||Número de mensajes que envió el usuario 1 durante la sesión.  <br/> |
|**User2MessageCount** <br/> |entero  <br/> ||Número de mensajes que envió el usuario 2 durante la sesión.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora al final de la sesión.  <br/> |
|**MediaTypes** <br/> |entero  <br/> ||Conjunto de bits que indica el tipo de medio de esta sesión. A continuación se enumeran las definiciones de los tipos:  <br/> 1- MI  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- VÍDEO  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Conjunto de bits que señala los atributos del usuario 1. Se enumeran las siguientes definiciones de atributo:  <br/> 0x01 - Integrado con el teléfono de escritorio  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Conjunto de bits que señala los atributos del usuario 2. Se enumeran las siguientes definiciones de atributo:  <br/> 0x01 - Integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:  <br/> 0x01 - Sesión reintentada  <br/> 0x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas  <br/> |
|**Procesado** <br/> |bit  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   
\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.
  

