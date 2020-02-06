---
title: Tabla ConferenceSessionDetails en Skype empresarial Server 2015
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
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.
ms.openlocfilehash: 95cf64589cdcd0fd38b4e29cd4e863c870f2a7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815348"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabla ConferenceSessionDetails en Skype empresarial Server 2015
 
Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Fechas  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión; se usa junto con **SessionIdSeq** para identificar de forma exclusiva una sesión de conferencia. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa junto con **SessionIdTime** para identificar de forma exclusiva una sesión de conferencia. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Extranjero  <br/> |Centrar el URI de conferencia relacionado con esta sesión. Para obtener más información, consulte la [tabla ConferenceUris en Skype empresarial Server 2015](conferenceuris.md) . Este URI es un URI de conferencia basado en el foco. <br/> |
|**ConfInstance** <br/> |Identificador  <br/> ||Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Extranjero  <br/> |URI de conferencia del servidor de conferencia relacionado con esta sesión. Para obtener más información, consulte la [tabla ConferenceUris en Skype empresarial Server 2015](conferenceuris.md) . Este URI es el URI de conferencia basado en el servidor de conferencia. Para sesiones de conferencia focalizadas, esta columna será nula. <br/> |
|**Iddeusuario** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR de un usuario en la sesión de conferencia. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**UserEndpointId** <br/> |identificador  <br/> ||Un GUID para identificar la instancia de Endpoint. Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un identificador de extremo diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Extranjero  <br/> |Indica el identificador del usuario de la persona que llama en nombre. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del usuario al que hace referencia la llamada. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Extranjero  <br/> |Versión del cliente usada por el usuario de la Conferencia. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Extranjero  <br/> |Versión de cliente usada por el servidor de conferencia. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Extranjero  <br/> |Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Extranjero  <br/> |Número de identificación para identificar la sesión. Se usa junto con **ReplacesDialogIdTime** para identificar de forma única una sesión que se reemplaza por esta sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica si la sesión ha sido iniciada por el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica si la sesión finalizó por el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si el usuario ha iniciado sesión en un interno o no.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta del Protocolo de inicio de sesión (SIP) a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del servidor front-end usado para esta sesión. Para obtener más información, consulte la [tabla servidores](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Extranjero  <br/> |IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la [tabla grupos](pools.md) . <br/> |
|**MediationServerId** <br/> |int  <br/> |Extranjero  <br/> |El servidor de mediación que usa la llamada. Para obtener más información, consulte la [tabla MediationServers](mediationservers.md) . <br/> |
|**GatewayId** <br/> |int  <br/> |Extranjero  <br/> |La puerta de enlace que usa la llamada. Para obtener más información, consulte la [tabla de puertas de enlace en Skype empresarial Server 2015](gateways.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Extranjero  <br/> |El servidor perimetral que usa la llamada. Para obtener más información, consulte la [tabla EdgeServers en Skype empresarial Server 2015](edgeservers.md) . <br/> |
|**ContentTypeId** <br/> |int  <br/> |Extranjero  <br/> |Tipo de contenido usado en la sesión. Para obtener más información, consulte la [tabla contentTypes en Skype empresarial Server 2015](contenttypes.md) . <br/> |
|**InviteTime** <br/> |datetime  <br/> ||La hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la primera respuesta del SIP. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||La hora de finalización de la sesión.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Extranjero  <br/> |Contiene el valor Type URI de MCU de la [tabla UriTypes](uritypes.md). Este campo se usa para mejorar el rendimiento de las consultas.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Un conjunto de bits que indica los atributos de usuario. Se muestran las siguientes definiciones de atributos: <br/>  Integrado con un teléfono de escritorio: 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Un conjunto de bits que indica los atributos de la llamada. Se muestran las siguientes definiciones de atributos: <br/>  Reintento de sesión: 1 <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.
  

