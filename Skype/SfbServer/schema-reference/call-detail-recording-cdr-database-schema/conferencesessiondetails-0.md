---
title: Tabla ConferenceSessionDetails en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.
ms.openlocfilehash: fc69150cf95ca0f00a4c1731aeda44f1e674a6cd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843673"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabla ConferenceSessionDetails en Skype Empresarial Server 2015
 
Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión; se usa junto con **SessionIdSeq para** identificar de forma única una sesión de conferencia. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa junto con **SessionIdTime para** identificar de forma única una sesión de conferencia. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. * <br/> |
|**ConferenceUriId** <br/> |Entero  <br/> |Externo  <br/> |URI de conferencia basada en Foco relacionada con esta sesión. Vea la [tabla ConferenceUris de Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. Esta URI es una URI de conferencia basada en Foco. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |Entero  <br/> |Externo  <br/> |URI de conferencia para servidor de conferencia relacionada con esta sesión. Vea la [tabla ConferenceUris de Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. Esta URI es la URI de conferencia basada en servidor de conferencia. En las sesiones de conferencia basadas en Foco, esta columna será nula. <br/> |
|**UserId** <br/> |Entero  <br/> |Externo  <br/> |Id. de un usuario en la sesión de conferencia. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.  <br/> |
|**OnBehalfOfId** <br/> |Entero  <br/> |Externo  <br/> |Señala el identificador de usuario en cuyo nombre llama el autor de la llamada. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |Entero  <br/> |Externo  <br/> |Identificador del usuario por el que se hace referencia a la sesión. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**UserClientVersionId** <br/> |Entero  <br/> |Externo  <br/> |Versión del cliente utilizada por el usuario de conferencia. Vea la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**ConfClientVersionId** <br/> |Entero  <br/> |Externo  <br/> |Versión del cliente utilizada por el usuario de servidor. Vea la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externo  <br/> |Número con el que se identifica el diálogo que se reemplazó por la sesión actual. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |Entero  <br/> |Externo  <br/> |Número con el que se identifica la sesión. Se usa junto con **ReplacesDialogIdTime** para identificar de manera exclusiva una sesión que se reemplazó por esta sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica si la sesión la inició el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica si la sesión la finalizó el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.  <br/> |
|**ResponseCode** <br/> |Entero  <br/> ||Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |Entero  <br/> ||Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**ServerId** <br/> |Entero  <br/> |Externo  <br/> |Identificador del servidor front-end usado en esta sesión. Vea la [tabla Servidores para](servers.md) obtener más información. <br/> |
|**PoolId** <br/> |Entero  <br/> |Externo  <br/> |Identificador del grupo en el que se capturó la sesión. Vea la [tabla Grupos de servidores](pools.md) para obtener más información. <br/> |
|**MediationServerId** <br/> |Entero  <br/> |Externo  <br/> |El servidor de mediación que está utilizando la llamada. Vea la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**GatewayId** <br/> |Entero  <br/> |Externo  <br/> |La puerta de enlace que está utilizando la llamada. Vea la tabla Puertas de enlace [de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |Entero  <br/> |Externo  <br/> |El servidor perimetral que está utilizando la llamada. Vea la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**ContentTypeId** <br/> |Entero  <br/> |Externo  <br/> |Tipo de contenido empleado en la sesión. Vea la [tabla ContentTypes en Skype Empresarial Server 2015](contenttypes.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la primera respuesta SIP. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora en que finalizó la sesión.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externo  <br/> |Contiene el valor de tipo URI MCU de la [tabla UriTypes](uritypes.md). Este campo se utiliza para mejorar el rendimiento de las consultas.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos: <br/>  Integrado con el teléfono de escritorio: 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo: <br/>  Reintento de sesión: 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   
\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.
  

