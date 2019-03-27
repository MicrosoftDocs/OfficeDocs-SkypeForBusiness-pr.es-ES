---
title: Lista de tablas de CDR de Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Los detalles de llamadas (CDR) esquema de base de datos consta de las siguientes tablas.
ms.openlocfilehash: 977c48b58c5b1d1c0f21fbac07a28ec6efb0bfd6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881203"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tablas de CDR de Skype para Business Server 2015
 
Los detalles de llamadas (CDR) esquema de base de datos consta de las siguientes tablas. 
  
## <a name="static-tables"></a>Tablas estáticas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla CallPriorities en Skype para Business Server 2015](callpriorities.md) <br/> |Almacena la lista de posibles prioridades de llamada, como emergencia, urgente, normal, no urgente y mucho más.  <br/> |
|[Tabla taba en Skype para Business Server 2015](conferencejointimethresholds.md) <br/> |Almacena los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia.  <br/> |
|[Tabla DeRegisterType en Skype para Business Server 2015](deregistertype.md) <br/> |Almacenes de la lista de usuario posible motivos, como "cliente inicia," de anulación "registro expirado",""bloqueo de cliente"y mucho más.  <br/> |
|[Tabla MediaList](medialist.md) <br/> |Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).  <br/> |
|[Tabla PurgeSettings](purgesettings.md) <br/> |Almacena información que especifica si (y cuando) obsoletos llamada registros de detalle se eliminarán automáticamente de la base de datos de CDR.  <br/> |
|[Tabla Roles](roles.md) <br/> |Almacena la lista de posibles roles de conferencia (por ejemplo, moderador y Asistente).  <br/> |
|[Tabla SIPResponseMetaData](sipresponsemetadata.md) <br/> |Almacena una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tablas auxiliares

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ClientVersions en Skype para Business Server 2015](clientversions.md) <br/> |Almacena a los clientes (ambos cliente tipo y número de versión) de cada cliente que participa en una llamada con información capturada en esta base de datos.  <br/> |
|[Tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) <br/> |Almacena una lista de Conferenceuri que se usa en la conferencia relacionada con las llamadas.  <br/> |
|[Tabla ContentTypes de Skype para Business Server 2015](contenttypes.md) <br/> |Almacena una lista de tipos de contenido de protocolo de inicio de sesión (SIP) que se usan en las llamadas de punto a punto y las llamadas de conferencia.  <br/> |
|[Tabla de dispositivos en Skype para Business Server 2015](devices.md) <br/> |Almacena una lista de dispositivos, incluido su fabricante, la versión de hardware y la dirección MAC.  <br/> |
|[Tabla de cuadros de diálogo en Skype para Business Server 2015](dialogs.md) <br/> |Almacena información sobre el identificador de diálogo para cada sesión en la base de datos.  <br/> |
|[Tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) <br/> |Almacena una lista de los servidores perimetrales que se usan para las llamadas externas.  <br/> |
|[Tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) <br/> |Almacena una lista de puertas de enlace que se usan para voz a través de las llamadas del protocolo de Internet (VoIP).  <br/> |
|[Tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) <br/> |Almacena una lista de las versiones de hardware de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla de los fabricantes de Skype para Business Server 2015](manufacturers.md) <br/> |Almacena una lista de los fabricantes de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla de MCU en Skype para Business Server 2015](mcus.md) <br/> |Almacena información acerca de los diversos / servidores de conferencia A/v y sus identificadores URI.  <br/> |
|[Tabla MediationServers](mediationservers.md) <br/> |Almacena una lista de los servidores de mediación que se usan para las llamadas VoIP.  <br/> |
|[Tabla Phones](phones.md) <br/> |Almacena todos los números de teléfono utilizados en las llamadas VoIP que se archivaron o cuyos detalles se registraron.  <br/> |
|[Tabla Pools](pools.md) <br/> |Almacena los nombres del grupo de servidores en qué mensajería instantánea se capturan los mensajes.  <br/> |
|[Tabla Servers](servers.md) <br/> |Almacena el nombre de los servidores que participan en las llamadas.  <br/> |
|[Tabla Tenants](tenants.md) <br/> |Almacena a los inquilinos compatibles con la implementación actual. Hay algunas inquilinos en compilación para usuario Enterprise, usuarios federados, usuarios de conectividad de mensajería instantánea públicos y los usuarios anónimos.  <br/> |
|[Tabla UserAgentDef](useragentdef.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla Users](users.md) <br/> |Almacena el usuario de URI de los usuarios que han participado en sesiones registran o archivan en esta base de datos.  <br/> |
|[Tabla UserStatistics](userstatistics.md) <br/> |Almacena información sobre el uso de un usuario concreto del sistema.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros CDR de conferencias

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de las conferencias en Skype para Business Server 2015](conferences.md) <br/> |Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluido el URI de conferencia y la hora de inicio y finalización.  <br/> |
|[Tabla ConferenceSessionDetails en Skype para Business Server 2015](conferencesessiondetails-0.md) <br/> |Almacena información acerca de cada sesión de conferencia basada en SIP, incluidos el inicio y hora de finalización, identificador de usuario, código de respuesta y el identificador de diagnóstico para cada sesión.  <br/> |
|[Tabla FocusJoinsAndLeaves en Skype para Business Server 2015](focusjoinsandleaves.md) <br/> |Almacena información acerca de la conferencia se une a y abandona, incluida la versión de cliente y el rol de los usuarios.  <br/> |
|[Tabla McuJoinsAndLeaves en Skype para Business Server 2015](mcujoinsandleaves.md) <br/> |Almacena información acerca de los servidores de conferencia A/v que participan en una conferencia y el usuario participar y deje veces.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tablas para mensajes en las conferencias de mensajería instantánea

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla ConferenceMessageCount en Skype para Business Server 2015](conferencemessagecount.md) <br/> |Para cada conferencia de mensajería instantánea, almacena el número de mensajes enviados por cada usuario.  <br/> |
|[Tabla IMReportSummary en Skype para Business Server 2015](imreportsummary.md) <br/> |Proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para las sesiones de punto a punto

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla SessionDetails](sessiondetails.md) <br/> |Almacena información acerca de cada sesión de punto a punto, incluidos el inicio y hora de finalización, identificador de usuario, código de respuesta y recuento de mensajes para cada usuario.  <br/> |
|[Tabla FileTransfers en Skype para Business Server 2015](filetransfers-0.md) <br/> |Almacena información acerca de la transferencia de archivos sesiones, incluido el archivo el nombre y resultado (aceptado, rechazado o cancelado).  <br/> |
|[Tabla Media](media.md) <br/> |Almacena información acerca de los diferentes tipos de medios implicados en las sesiones de punto a punto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabla de detalles de llamadas de VoIP

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla VoipDetails](voipdetails-0.md) <br/> |Para cada llamada de VoIP y RTC entre dos participantes, almacena información acerca de la llamada, como el teléfono teléfono identificador de VoIP, puerta de enlace usada y qué parte desconectado. Hace referencia a la [tabla SessionDetails](sessiondetails.md) para horas de inicio/fin de llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Si una de las partes en una llamada es un usuario de VoIP o un servidor de mediación participó en la llamada, se creará un registro en esta tabla. Información sobre las llamadas de VoIP y VoIP que no impliquen un (RTC) de la red telefónica conmutada se captura en la [tabla SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabla de auditoría de llamadas E9-1-1

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de ubicaciones de Skype para Business Server 2015](locations.md) <br/> |Para cada llamada de emergencia, como una llamada de 9-1-1 mejorado (E9-1-1), almacena información de ubicación de la llamada. Hace referencia a la [tabla SessionDetails](sessiondetails.md) para horas de inicio/fin de llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Esta tabla contiene sólo el blob de ubicación para la llamada de E9-1-1. Hace referencia a la tabla SessionDetails para otra información detallada acerca de la llamada. 
  
## <a name="tables-for-troubleshooting"></a>Tablas para solución de problemas

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla de la aplicación en Skype para Business Server 2015](application.md) <br/> |Almacena información acerca de los diferentes procesos de Skype para Business Server 2015 que participan en el enrutamiento y las conexiones.  <br/> |
|[Tabla CallType en Skype para Business Server 2015](calltype.md) <br/> |Almacena información acerca de los tipos de la llamada, por ejemplo, "audio", "Mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".  <br/> |
|[Tabla de categoría de error de Skype para Business Server 2015](errorcategory.md) <br/> |Almacena el nombre descriptivo para cada Skype para la clasificación de diagnóstico Business Server 2015.  <br/> |
|[Tabla ErrorDef en Skype para Business Server 2015](errordef.md) <br/> |Almacena información acerca de los tipos de errores y sus definiciones.  <br/> |
|[Tabla ErrorReport en Skype para Business Server 2015](errorreport.md) <br/> |Almacena información acerca de los errores que se han producido.  <br/> |
|[Tabla ProgressReport](progressreport.md) <br/> |Almacena información acerca de los informes de progreso de los diferentes pasos implicados en Skype para los procesos de negocio Server 2015.  <br/> |
   
En las tablas de la siguiente lista se usan internamente por Skype para Business Server 2015. Sus detalles no se describen en este documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tablas para uso interno de Lync Server

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Sólo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Sólo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Sólo para uso interno.  <br/> |
|**Tabla FrontEnd** <br/> |Sólo para uso interno.  <br/> |
|**Tabla MSMQProcessing** <br/> |Sólo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**Tabla syndicators** <br/> |Sólo para uso interno.  <br/> |
|**Tabla SyndicatorsTenantMap** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Sólo para uso interno.  <br/> |
|**UserStatistics** <br/> |Sólo para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Sólo para uso interno.  <br/> |
|**UsageSummary** <br/> |Sólo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Sólo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**TimeZones** <br/> |Sólo para uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Sólo para uso interno.  <br/> |
|**FailureSummary** <br/> |Sólo para uso interno.  <br/> |
|**ServerSummary** <br/> |Sólo para uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Sólo para uso interno.  <br/> |
   

