---
title: Lista de tablas de CDR en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: El esquema de la base de datos de grabación de detalles de llamadas (CDR) consta de las siguientes tablas.
ms.openlocfilehash: a35636333366bbfd55d4337fadfec68af681db6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815138"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tablas de CDR en Skype empresarial Server 2015
 
El esquema de la base de datos de grabación de detalles de llamadas (CDR) consta de las siguientes tablas. 
  
## <a name="static-tables"></a>Tablas estáticas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla CallPriorities en Skype empresarial Server 2015](callpriorities.md) <br/> |Almacena la lista de posibles prioridades de llamadas, como emergencia, urgente, normal, no urgentes, etc.  <br/> |
|[Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015](conferencejointimethresholds.md) <br/> |Almacena los límites de clasificación usados por el informe de Resumen de tiempo de combinación de conferencia.  <br/> |
|[Tabla DeRegisterType en Skype empresarial Server 2015](deregistertype.md) <br/> |Almacena la lista de posibles razones de anulación del registro de usuarios, como "cliente iniciado", "registro expirado", "bloqueo del cliente", etc.  <br/> |
|[Tabla MediaList](medialist.md) <br/> |Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).  <br/> |
|[Tabla PurgeSettings](purgesettings.md) <br/> |Almacena información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR.  <br/> |
|[Tabla Roles](roles.md) <br/> |Almacena la lista de posibles roles de conferencia (por ejemplo, asistente y moderador).  <br/> |
|[Tabla SIPResponseMetaData](sipresponsemetadata.md) <br/> |Almacena una lista de códigos de respuesta SIP, así como la clasificación y definición de cada uno de esos códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tablas de soporte técnico

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) <br/> |Almacena los clientes (tanto el tipo de cliente como el número de versión) de cada cliente implicado en una llamada con información capturada en esta base de datos.  <br/> |
|[Tabla ConferenceUris en Skype empresarial Server 2015](conferenceuris.md) <br/> |Almacena una lista de ConferenceURIs que se usan en llamadas relacionadas con la Conferencia.  <br/> |
|[Tabla ContentTypes en Skype empresarial Server 2015](contenttypes.md) <br/> |Almacena una lista de tipos de contenido de protocolo de inicio de sesión (SIP) que se usan en las llamadas de punto a punto y en las llamadas en conferencia.  <br/> |
|[Tabla dispositivos de Skype empresarial Server 2015](devices.md) <br/> |Almacena una lista de dispositivos, incluidos el fabricante, la versión de hardware y la dirección MAC.  <br/> |
|[Tabla de cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) <br/> |Almacena información sobre el identificador de cuadro de diálogo para cada sesión de la base de datos.  <br/> |
|[Tabla EdgeServers en Skype empresarial Server 2015](edgeservers.md) <br/> |Almacena una lista de servidores perimetrales que se usan para llamadas externas.  <br/> |
|[Tabla de puertas de enlace en Skype empresarial Server 2015](gateways.md) <br/> |Almacena una lista de puertas de enlace que se usan para llamadas de protocolo de voz a través de Internet (VoIP).  <br/> |
|[Tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) <br/> |Almacena una lista de versiones de hardware de los dispositivos (teléfono de escritorio).  <br/> |
|[Tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) <br/> |Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla MCU en Skype empresarial Server 2015](mcus.md) <br/> |Almacena información acerca de los diversos servidores de conferencia A/V y sus URI.  <br/> |
|[Tabla MediationServers](mediationservers.md) <br/> |Almacena una lista de servidores de mediación que se usan para llamadas de VoIP.  <br/> |
|[Tabla Phones](phones.md) <br/> |Almacena todos los números de teléfono usados en llamadas VoIP que fueron archivados o cuyos detalles de llamadas fueron grabados.  <br/> |
|[Tabla Pools](pools.md) <br/> |Almacena los nombres del grupo en el que se capturan los mensajes INSTANTÁNEos.  <br/> |
|[Tabla Servers](servers.md) <br/> |Almacena el nombre de los servidores implicados en las llamadas.  <br/> |
|[Tabla Tenants](tenants.md) <br/> |Almacena los espacios empresariales admitidos por la implementación actual. Hay algunos inquilinos de compilación para usuarios de empresa, usuarios federados, usuarios de la conectividad de mensajería instantánea pública y usuarios anónimos.  <br/> |
|[Tabla UserAgentDef](useragentdef.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla Users](users.md) <br/> |Almacena los URI de usuario de los usuarios que participaron en sesiones grabadas o archivadas en esta base de datos.  <br/> |
|[Tabla UserStatistics](userstatistics.md) <br/> |Almacena información sobre el uso del sistema por un usuario individual.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros de CDR de conferencia

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla conferencias en Skype empresarial Server 2015](conferences.md) <br/> |Almacena información sobre todas las conferencias que se archivaron o cuyos detalles se grabaron, incluyendo ConferenceURI, y la hora de inicio y finalización.  <br/> |
|[Tabla ConferenceSessionDetails en Skype empresarial Server 2015](conferencesessiondetails-0.md) <br/> |Almacena información sobre todas las sesiones de conferencia basadas en SIP, como la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.  <br/> |
|[Tabla FocusJoinsAndLeaves en Skype empresarial Server 2015](focusjoinsandleaves.md) <br/> |Almacena información acerca de las uniones y las hojas de reuniones, incluidos el rol de los usuarios y la versión del cliente.  <br/> |
|[Tabla McuJoinsAndLeaves en Skype empresarial Server 2015](mcujoinsandleaves.md) <br/> |Almacena información sobre los servidores de conferencia A/V implicados en una conferencia y la combinación de usuarios y horas de salida.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tablas de mensajes en conferencias de mensajería instantánea

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ConferenceMessageCount en Skype empresarial Server 2015](conferencemessagecount.md) <br/> |Para cada Conferencia de mensajería instantánea, almacena el número de mensajes que envió cada usuario.  <br/> |
|[Tabla IMReportSummary en Skype empresarial Server 2015](imreportsummary.md) <br/> |Proporciona un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para sesiones de punto a punto

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla SessionDetails](sessiondetails.md) <br/> |Almacena información sobre cada sesión de punto a punto, incluyendo la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.  <br/> |
|[Tabla FileTransfers en Skype empresarial Server 2015](filetransfers-0.md) <br/> |Almacena información sobre las sesiones de transferencia de archivos, incluidos el nombre de archivo y el resultado (aceptada, rechazada o cancelada).  <br/> |
|[Tabla Media](media.md) <br/> |Almacena información sobre los diferentes tipos de medios implicados en sesiones de punto a punto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabla de detalles de llamadas VoIP

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla VoipDetails](voipdetails-0.md) <br/> |Para cada llamada de VoIP/RTC de dos partes, almacena información sobre la llamada, como el identificador de teléfono del teléfono VoIP, la puerta de enlace usada y qué parte se desconectó. Hace referencia a la [tabla SessionDetails](sessiondetails.md) para las horas de inicio y finalización de la llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Si una de las partes de una llamada es un usuario de VoIP o si un servidor de mediación participó en la llamada, se creará un registro en esta tabla. La información sobre las llamadas de VoIP o VoIP que no implica un teléfono de red de telefonía pública conmutada (RTC) se captura en la [tabla SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabla de auditorías de llamadas de E9-1-1

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla localidades en Skype empresarial Server 2015](locations.md) <br/> |Para cada llamada de emergencia, como una llamada mejorada de 9-1-1 (E9-1-1), almacena información sobre la ubicación de la llamada. Hace referencia a la [tabla SessionDetails](sessiondetails.md) para las horas de inicio y finalización de la llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Esta tabla solo contiene el BLOB de ubicación para la llamada de E9-1-1. Hace referencia a la tabla SessionDetails para obtener información detallada sobre la llamada. 
  
## <a name="tables-for-troubleshooting"></a>Tablas para la solución de problemas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de aplicaciones en Skype empresarial Server 2015](application.md) <br/> |Almacena información acerca de los distintos procesos de Skype empresarial Server 2015 que participan en el enrutamiento y en las conexiones.  <br/> |
|[Tabla CallType en Skype empresarial Server 2015](calltype.md) <br/> |Almacena información sobre los tipos de la llamada, como "audio", "mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".  <br/> |
|[Tabla ErrorCategory en Skype empresarial Server 2015](errorcategory.md) <br/> |Almacena el nombre descriptivo de cada clasificación de diagnóstico de Skype empresarial Server 2015.  <br/> |
|[Tabla ErrorDef en Skype empresarial Server 2015](errordef.md) <br/> |Almacena información sobre los tipos de errores y sus definiciones.  <br/> |
|[Tabla ErrorReport en Skype empresarial Server 2015](errorreport.md) <br/> |Almacena información sobre los errores que se han producido.  <br/> |
|[Tabla ProgressReport](progressreport.md) <br/> |Almacena información sobre los informes de progreso de varios pasos relacionados con los procesos de Skype empresarial Server 2015.  <br/> |
   
Las tablas de la siguiente lista son utilizadas internamente por Skype empresarial Server 2015. Los detalles no se describen en este documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tablas para uso interno de Lync Server

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Solo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Solo para uso interno.  <br/> |
|**Tabla de FrontEnd** <br/> |Solo para uso interno.  <br/> |
|**Tabla MSMQProcessing** <br/> |Solo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo para uso interno.  <br/> |
|**Tabla de sindicación** <br/> |Solo para uso interno.  <br/> |
|**Tabla SyndicatorsTenantMap** <br/> |Solo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Solo para uso interno.  <br/> |
|**UserStatistics** <br/> |Solo para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Solo para uso interno.  <br/> |
|**UsageSummary** <br/> |Solo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo para uso interno.  <br/> |
|**TimeZones** <br/> |Solo para uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Solo para uso interno.  <br/> |
|**FailureSummary** <br/> |Solo para uso interno.  <br/> |
|**ServerSummary** <br/> |Solo para uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Solo para uso interno.  <br/> |
   

