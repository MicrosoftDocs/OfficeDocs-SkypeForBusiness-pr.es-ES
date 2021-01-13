---
title: Tabla ConferenceSessionDetails en Skype Empresarial Server 2015
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
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.
ms.openlocfilehash: 7eb00976af71e88c9bfe2348c4b2e91ca5bb23f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816200"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabla ConferenceSessionDetails en Skype Empresarial Server 2015
 
Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión; se usa junto con **SessionIdSeq para** identificar de forma única una sesión de conferencia. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa junto con **SessionIdTime para** identificar de forma única una sesión de conferencia. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. * <br/> |
|**ConferenceUriId** <br/> |entero  <br/> |Externo  <br/> |URI de conferencia basada en Foco relacionada con esta sesión. Consulte la [tabla ConferenceUris en Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. Esta URI es una URI de conferencia basada en Foco. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificador que distingue entre instancias de conferencias recurrentes. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |entero  <br/> |Externo  <br/> |URI de conferencia para servidor de conferencia relacionada con esta sesión. Consulte la [tabla ConferenceUris en Skype Empresarial Server 2015](conferenceuris.md) para obtener más información. Esta URI es la URI de conferencia basada en servidor de conferencia. En las sesiones de conferencia basadas en Foco, esta columna será nula. <br/> |
|**UserId** <br/> |entero  <br/> |Externo  <br/> |Identificador de un usuario en la sesión de conferencia. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.  <br/> |
|**OnBehalfOfId** <br/> |entero  <br/> |Externo  <br/> |Señala el identificador de usuario en cuyo nombre llama el autor de la llamada. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |entero  <br/> |Externo  <br/> |Identificador del usuario por el que se hace referencia a la sesión. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**UserClientVersionId** <br/> |entero  <br/> |Externo  <br/> |Versión del cliente utilizada por el usuario de conferencia. Consulte la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**ConfClientVersionId** <br/> |entero  <br/> |Externo  <br/> |Versión del cliente utilizada por el usuario de servidor. Consulte la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externo  <br/> |Número con el que se identifica el diálogo que se reemplazó por la sesión actual. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |entero  <br/> |Externo  <br/> |Número con el que se identifica la sesión. Se usa junto con **ReplacesDialogIdTime** para identificar de manera exclusiva una sesión que se reemplazó por esta sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica si la sesión la inició el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica si la sesión la finalizó el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.  <br/> |
|**ResponseCode** <br/> |entero  <br/> ||Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |entero  <br/> ||Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**ServerId** <br/> |entero  <br/> |Externo  <br/> |Identificador del servidor front-end usado en esta sesión. Vea la [tabla Servidores para](servers.md) obtener más información. <br/> |
|**PoolId** <br/> |entero  <br/> |Externo  <br/> |Identificador del grupo en el que se capturó la sesión. Vea la tabla [Grupos de](pools.md) servidores para obtener más información. <br/> |
|**MediationServerId** <br/> |entero  <br/> |Externo  <br/> |El servidor de mediación que está utilizando la llamada. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**GatewayId** <br/> |entero  <br/> |Externo  <br/> |La puerta de enlace que está utilizando la llamada. Consulte la [tabla Puertas de enlace de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |entero  <br/> |Externo  <br/> |El servidor perimetral que está utilizando la llamada. Consulte la [tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) para obtener más información. <br/> |
|**ContentTypeId** <br/> |entero  <br/> |Externo  <br/> |Tipo de contenido empleado en la sesión. Consulte la [tabla ContentTypes en Skype Empresarial Server 2015](contenttypes.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la primera respuesta SIP. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora en que finalizó la sesión.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externo  <br/> |Contiene el valor de tipo uri de MCU de la [tabla UriTypes](uritypes.md). Este campo se utiliza para mejorar el rendimiento de las consultas.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos: <br/>  Integrado con el teléfono de escritorio: 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo: <br/>  Reintento de sesión: 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   
\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.
  

