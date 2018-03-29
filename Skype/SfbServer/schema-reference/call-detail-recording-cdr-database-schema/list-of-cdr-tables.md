---
title: Lista de tablas de CDR de Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: El detalle de llamada grabación de esquema de base de datos (CDR) consta de las siguientes tablas.
ms.openlocfilehash: 7e224b8170ec078cafaec2fe3cbf4cf9819eba41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tablas de CDR de Skype para Business Server 2015
 
El detalle de llamada grabación de esquema de base de datos (CDR) consta de las siguientes tablas. 
  
## <a name="static-tables"></a>Tablas estáticas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla CallPriorities en Skype para Business Server 2015](callpriorities.md) <br/> |Almacena la lista de prioridades se puede llamar de emergencia, urgente, normal, no urgente y mucho más.  <br/> |
|[Tabla ConferenceJoinTimeThresholds en Skype para Business Server 2015](conferencejointimethresholds.md) <br/> |Almacena los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia.  <br/> |
|[Tabla DeRegisterType en Skype para Business Server 2015](deregistertype.md) <br/> |Almacenes de anular el registro de la lista de usuario posibles razones, como "cliente iniciado," registro "ha vencido", "bloqueo de cliente" y mucho más.  <br/> |
|[Tabla mediaList](medialist.md) <br/> |Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).  <br/> |
|[Tabla PurgeSettings](purgesettings.md) <br/> |Almacena información que especifica si (y cuándo) anticuados llamada registros de detalle se eliminarán automáticamente de la base de datos de CDR.  <br/> |
|[Tabla de funciones](roles.md) <br/> |Almacena la lista de funciones de conferencia posible (por ejemplo, asistentes y moderador).  <br/> |
|[Tabla SIPResponseMetaData](sipresponsemetadata.md) <br/> |Almacena una lista de códigos de respuesta SIP y la clasificación y la definición de cada uno de dichos códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tablas de soporte

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ClientVersions en Skype para Business Server 2015](clientversions.md) <br/> |Almacena a los clientes (ambos cliente tipo y número de versión) de cada cliente que participan en una llamada con información capturada en esta base de datos.  <br/> |
|[Tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) <br/> |Llamadas relacionadas con almacena una lista de ConferenceURIs que se utilizan en la conferencia.  <br/> |
|[Tabla de tipos de contenido en Skype para Business Server 2015](contenttypes.md) <br/> |Almacena una lista de tipos de contenido de protocolo de inicio de sesión (SIP) que se utilizan en llamadas de punto a punto y conferencias telefónicas.  <br/> |
|[Tabla de dispositivos en Skype para Business Server 2015](devices.md) <br/> |Almacena una lista de dispositivos, incluyendo su fabricante, la versión de hardware y la dirección MAC.  <br/> |
|[Tabla de cuadros de diálogo en Skype para Business Server 2015](dialogs.md) <br/> |Almacena información sobre el identificador del cuadro de diálogo para cada sesión en la base de datos.  <br/> |
|[Tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) <br/> |Almacena una lista de servidores de borde que se utilizan para llamadas externas.  <br/> |
|[Tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) <br/> |Almacena una lista de puertas de enlace que se utilizan para voz sobre Protocolo Internet (VoIP) llamadas.  <br/> |
|[Tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) <br/> |Almacena una lista de las versiones de hardware de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla de fabricantes en Skype para Business Server 2015](manufacturers.md) <br/> |Almacena una lista de los fabricantes de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla de MCU en Skype para Business Server 2015](mcus.md) <br/> |Almacena información acerca de los distintos A / V servidores de conferencia y sus identificadores URI.  <br/> |
|[Tabla MediationServers](mediationservers.md) <br/> |Almacena una lista de servidores de mediación que se utilizan para las llamadas de VoIP.  <br/> |
|[Tabla de teléfonos](phones.md) <br/> |Almacena todos los números de teléfono utilizados en llamadas de VoIP que se archivaron o se grabaron cuyos detalles de llamada.  <br/> |
|[Tabla de grupos](pools.md) <br/> |Almacena los nombres de la agrupación en que mensajería instantánea, los mensajes se capturan.  <br/> |
|[Tabla de servidores](servers.md) <br/> |Almacena el nombre de los servidores implicados en las llamadas.  <br/> |
|[Tabla de inquilinos](tenants.md) <br/> |Almacena a los inquilinos compatibles con la implementación actual. Hay algunos inquilinos de generación para el usuario empresarial, usuario federado, usuario de conectividad de mensajería instantánea pública y los usuarios anónimos.  <br/> |
|[Tabla UserAgentDef](useragentdef.md) <br/> |Asigna identificadores de agente de usuario a nombres descriptivos del agente.  <br/> |
|[Tabla de usuarios](users.md) <br/> |Almacena el usuario los URI de usuarios que han participado en sesiones registrados o archivan en esta base de datos.  <br/> |
|[Tabla UserStatistics](userstatistics.md) <br/> |Almacena información acerca del uso de un usuario individual del sistema.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros CDR de conferencia

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Mesa de conferencias en Skype para Business Server 2015](conferences.md) <br/> |Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluidos ConferenceURI y hora inicial y final.  <br/> |
|[Tabla ConferenceSessionDetails en Skype para Business Server 2015](conferencesessiondetails-0.md) <br/> |Almacena información acerca de cada sesión de conferencia basada en SIP, incluyendo inicio y hora de finalización, ID de usuario, código de respuesta y diagnóstico ID para cada sesión.  <br/> |
|[Tabla FocusJoinsAndLeaves en Skype para Business Server 2015](focusjoinsandleaves.md) <br/> |Almacena información sobre la conferencia se une y deja, incluso la versión de cliente y rol de los usuarios.  <br/> |
|[Tabla McuJoinsAndLeaves en Skype para Business Server 2015](mcujoinsandleaves.md) <br/> |Almacena información acerca de la A / V conferencia servidores que participan en una conferencia y el usuario y dejen veces.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tablas de mensajes en conferencias de mensajería instantánea

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ConferenceMessageCount en Skype para Business Server 2015](conferencemessagecount.md) <br/> |Para cada conferencia de mensajes Instantáneos, almacena el número de mensajes enviados por cada usuario.  <br/> |
|[Tabla IMReportSummary en Skype para Business Server 2015](imreportsummary.md) <br/> |Proporciona un informe general sobre la celebrada en una organización de sesiones de mensajería instantánea.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para la sesiones de Peer-to-Peer

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla SessionDetails](sessiondetails.md) <br/> |Almacena información sobre cada sesión peer-to-peer, inicio y hora de finalización, ID de usuario, código de respuesta y el número de mensajes para cada usuario.  <br/> |
|[Tabla Bloqueandote en Skype para Business Server 2015](filetransfers-0.md) <br/> |Almacena información sobre la transferencia de archivos, sesiones, incluyendo el archivo de nombre y como resultado (aceptado, rechazado o cancelado).  <br/> |
|[Tabla de medios](media.md) <br/> |Almacena información sobre los diferentes tipos de medios implicados en las sesiones de peer-to-peer.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabla de detalles de llamadas de VoIP

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla VoipDetails](voipdetails-0.md) <br/> |Para cada llamada de VoIP/PSTN de dos partes, almacena información sobre la llamada, como el ID de VoIP teléfono teléfono, puerta de enlace utilizado y qué partido desconectado. Hace referencia a la [tabla de SessionDetails](sessiondetails.md) para las horas de inicio/fin de llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Si una de las partes en una llamada es un usuario de VoIP o un servidor de mediación participó en la llamada, se creará un registro en esta tabla. Información sobre llamadas de VoIP/VoIP no impliquen un teléfono de telefónica pública conmutada (PSTN) de red se captura en la [tabla SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabla de auditoría llamada E9-1-1

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de ubicaciones en Skype para Business Server 2015](locations.md) <br/> |Para cada llamada de emergencia, como una llamada Enhanced 9-1-1 (E9-1-1), almacena información sobre la llamada. Hace referencia a la [tabla de SessionDetails](sessiondetails.md) para las horas de inicio/fin de llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Esta tabla contiene sólo el blob de ubicación para la llamada E9-1-1. Hace referencia a la tabla SessionDetails para otra información detallada sobre la llamada. 
  
## <a name="tables-for-troubleshooting"></a>Tablas para solucionar problemas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de aplicación de Skype para Business Server 2015](application.md) <br/> |Almacena información sobre diversos procesos de Skype para el año 2015 de servidor empresariales que intervienen en las rutas y las conexiones.  <br/> |
|[Tabla de CallType en Skype para Business Server 2015](calltype.md) <br/> |Almacena información acerca de los tipos de la llamada, por ejemplo, "audio", "Mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".  <br/> |
|[Tabla ErrorCategory en Skype para Business Server 2015](errorcategory.md) <br/> |Almacena el nombre descriptivo de cada Skype para clasificación diagnóstico Business Server 2015.  <br/> |
|[Tabla ErrorDef en Skype para Business Server 2015](errordef.md) <br/> |Almacena información acerca de los tipos de errores y sus definiciones.  <br/> |
|[Tabla de ErrorReport en Skype para Business Server 2015](errorreport.md) <br/> |Almacena información acerca de los errores que se han producido.  <br/> |
|[Tabla ProgressReport](progressreport.md) <br/> |Almacena información acerca de los informes de progreso de varios pasos implicados en Skype para los procesos de negocio servidor 2015.  <br/> |
   
Las tablas de la lista siguiente se utilizan internamente por Skype para Business Server 2015. Los detalles no se describen en este documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tablas para uso interno de Lync Server

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Sólo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Sólo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de front-end** <br/> |Sólo para uso interno.  <br/> |
|**Tabla MSMQProcessing** <br/> |Sólo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**Tabla sindicadores** <br/> |Sólo para uso interno.  <br/> |
|**Tabla SyndicatorsTenantMap** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Sólo para uso interno.  <br/> |
|**UserStatistics** <br/> |Sólo para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Sólo para uso interno.  <br/> |
|**UsageSummary** <br/> |Sólo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Sólo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**Zonas horarias** <br/> |Sólo para uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Sólo para uso interno.  <br/> |
|**FailureSummary** <br/> |Sólo para uso interno.  <br/> |
|**ServerSummary** <br/> |Sólo para uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Sólo para uso interno.  <br/> |
   

