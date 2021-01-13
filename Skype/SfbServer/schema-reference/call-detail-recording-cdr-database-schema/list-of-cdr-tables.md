---
title: Lista de tablas de CDR en Skype Empresarial Server 2015
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
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: El esquema de la base de datos del registro detallado de llamadas (CDR) incluye las tablas siguientes.
ms.openlocfilehash: 7bd76a4cf374e72582c585908309605c4845454e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827600"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tablas de CDR en Skype Empresarial Server 2015
 
El esquema de la base de datos del registro detallado de llamadas (CDR) incluye las tablas siguientes. 
  
## <a name="static-tables"></a>Tablas estáticas

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla CallPriorities en Skype Empresarial Server 2015](callpriorities.md) <br/> |Almacena la lista de posibles prioridades de llamada, como emergencia, urgente, normal, no urgente, etc.  <br/> |
|[Tabla ConferenceJoinTimeThresholds en Skype Empresarial Server 2015](conferencejointimethresholds.md) <br/> |Almacena los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia.  <br/> |
|[Tabla DeRegisterType en Skype Empresarial Server 2015](deregistertype.md) <br/> |Almacena la lista de posibles motivos de anulación del registro de usuario, como "iniciado por cliente", "registro expirado", "bloqueo de cliente", etc.  <br/> |
|[Tabla MediaList](medialist.md) <br/> |Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).  <br/> |
|[Tabla PurgeSettings](purgesettings.md) <br/> |Almacena información que especifica si los registros de detalles de llamadas no actualizados se eliminarán automáticamente de la base de datos de CDR (así como cuándo se eliminarán).  <br/> |
|[Tabla Roles](roles.md) <br/> |Almacena la lista de posibles roles de conferencia (por ejemplo, participante y moderador).  <br/> |
|[Tabla SIPResponseMetaData](sipresponsemetadata.md) <br/> |Almacena una lista de códigos de respuesta SIP, así como una clasificación y una definición de cada uno de estos códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tablas auxiliares

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) <br/> |Almacena los clientes (tipo de cliente y número de versión) de cada cliente que participa de una llamada con información capturada en esta base de datos.  <br/> |
|[Tabla ConferenceUris en Skype Empresarial Server 2015](conferenceuris.md) <br/> |Almacena una lista de ConferenceURI utilizados en las llamadas de conferencia.  <br/> |
|[Tabla ContentTypes en Skype Empresarial Server 2015](contenttypes.md) <br/> |Almacena una lista de tipos de contenido del Protocolo de inicio de sesión (SIP) utilizados en las llamadas punto a punto y las llamadas de conferencia.  <br/> |
|[Tabla Devices en Skype Empresarial Server 2015](devices.md) <br/> |Almacena una lista de dispositivos, incluido el fabricante, la versión de hardware y la dirección MAC.  <br/> |
|[Tabla Dialogs en Skype Empresarial Server 2015](dialogs.md) <br/> |Almacena información acerca del identificador de diálogo de cada sesión de la base de datos.  <br/> |
|[Tabla EdgeServers en Skype Empresarial Server 2015](edgeservers.md) <br/> |Almacena una lista de servidores perimetrales utilizados para las llamadas externas.  <br/> |
|[Tabla Gateways en Skype Empresarial Server 2015](gateways.md) <br/> |Almacena una lista de puertas de enlace utilizadas para las llamadas de voz sobre IP (VoIP).  <br/> |
|[Tabla HardwareVersions en Skype Empresarial Server 2015](hardwareversions.md) <br/> |Almacena una lista de versiones de hardware de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla Manufacturers en Skype Empresarial Server 2015](manufacturers.md) <br/> |Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).  <br/> |
|[Tabla Mcus en Skype Empresarial Server 2015](mcus.md) <br/> |Almacena información acerca de los diferentes servidores de conferencia A/V y sus URI.  <br/> |
|[Tabla MediationServers](mediationservers.md) <br/> |Almacena una lista de servidores de mediación utilizados para las llamadas VoIP.  <br/> |
|[Tabla Teléfonos](phones.md) <br/> |Almacena todos los números de teléfono utilizados en las llamadas VoIP que se archivaron o cuyos detalles se registraron.  <br/> |
|[Tabla Pools](pools.md) <br/> |Almacena los nombres del grupo de servidores en el que se capturan los mensajes instantáneos.  <br/> |
|[Tabla Servers](servers.md) <br/> |Almacena el nombre de los servidores que participan en llamadas.  <br/> |
|[Tabla Tenants](tenants.md) <br/> |Almacena los inquilinos admitidos por la implementación actual. Existen inquilinos integrados para usuarios de empresa, federados, de conectividad de mensajería instantánea pública y anónimos.  <br/> |
|[Tabla UserAgentDef](useragentdef.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla Users](users.md) <br/> |Almacena los URI de los usuarios que participaron de sesiones registradas o archivadas en esta base de datos.  <br/> |
|[Tabla UserStatistics](userstatistics.md) <br/> |Almacena información sobre el uso del sistema por parte de un usuario individual.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros CDR de conferencias

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla Conferences en Skype Empresarial Server 2015](conferences.md) <br/> |Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluido el URI de conferencia, y la hora de inicio y de finalización.  <br/> |
|[Tabla ConferenceSessionDetails en Skype Empresarial Server 2015](conferencesessiondetails-0.md) <br/> |Almacena información acerca de cada sesión de conferencia basada en SIP, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.  <br/> |
|[Tabla FocusJoinsAndLeaves en Skype Empresarial Server 2015](focusjoinsandleaves.md) <br/> |Almacena información sobre las combinaciones y las hojas de conferencia, incluido el rol de los usuarios y la versión del cliente.  <br/> |
|[Tabla McuJoinsAndLeaves en Skype Empresarial Server 2015](mcujoinsandleaves.md) <br/> |Almacena información acerca de los servidores de conferencia A/V utilizados en una conferencia, y la hora de conexión y desconexión del usuario.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tablas para mensajes de conferencias de mensajería instantánea

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla ConferenceMessageCount en Skype Empresarial Server 2015](conferencemessagecount.md) <br/> |Para cada conferencia de mensajería instantánea, almacena el número de mensajes enviados por cada usuario.  <br/> |
|[Tabla IMReportSummary en Skype Empresarial Server 2015](imreportsummary.md) <br/> |Proporciona un informe general de las sesiones de mensajería instantánea llevadas a cabo en una organización.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para sesiones punto a punto

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla SessionDetails](sessiondetails.md) <br/> |Almacena información acerca de cada sesión punto a punto, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.  <br/> |
|[Tabla FileTransfers en Skype Empresarial Server 2015](filetransfers-0.md) <br/> |Almacena información acerca de las sesiones de transferencia de archivos, incluido el nombre de archivo y el resultado (aceptado, rechazado o cancelado).  <br/> |
|[Tabla Multimedia](media.md) <br/> |Almacena información acerca de los diferentes tipos de medios utilizados en las sesiones punto a punto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabla para detalles de llamadas VoIP

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla VoipDetails](voipdetails-0.md) <br/> |Para cada llamada VoIP/RTC de dos participantes, almacena información acerca de la llamada, como el identificador del teléfono VoIP, la puerta de enlace utilizada y el participante que desconectó la llamada. Hace referencia a [la tabla SessionDetails para](sessiondetails.md) las horas de inicio y finalización de la llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Si un participante de la llamada es un usuario VoIP o si se utilizó un servidor de mediación en la llamada, se creará un registro en esta tabla. La información sobre las llamadas VoIP/VoIP que no implican un teléfono de red telefónica conmutada (RTC) se captura en la tabla [SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabla para auditoría de llamadas E9-1-1

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla Ubicaciones en Skype Empresarial Server 2015](locations.md) <br/> |Para cada llamada de emergencia, como una llamada Enhanced 9-1-1 (E9-1-1), almacena información acerca de la ubicación de la llamada. Hace referencia a [la tabla SessionDetails para](sessiondetails.md) las horas de inicio y finalización de la llamada y el código de respuesta. <br/> |
   
> [!NOTE]
> Esta tabla solamente contiene el objeto binario grande de la ubicación de la llamada E9-1-1. Remítase a la tabla SessionDetails para obtener información adicional sobre la llamada. 
  
## <a name="tables-for-troubleshooting"></a>Tablas para solución de problemas

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla Application en Skype Empresarial Server 2015](application.md) <br/> |Almacena información sobre los distintos procesos de Skype Empresarial Server 2015 implicados en el enrutamiento y las conexiones.  <br/> |
|[Tabla CallType en Skype Empresarial Server 2015](calltype.md) <br/> |Almacena información sobre los tipos de llamada, como "audio", "Mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".  <br/> |
|[Tabla ErrorCategory en Skype Empresarial Server 2015](errorcategory.md) <br/> |Almacena el nombre descriptivo de cada clasificación de diagnóstico de Skype Empresarial Server 2015.  <br/> |
|[Tabla ErrorDef en Skype Empresarial Server 2015](errordef.md) <br/> |Almacena información acerca de los tipos de errores y sus definiciones.  <br/> |
|[Tabla ErrorReport en Skype Empresarial Server 2015](errorreport.md) <br/> |Almacena información acerca de los errores generados.  <br/> |
|[Tabla ProgressReport](progressreport.md) <br/> |Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de Skype Empresarial Server 2015.  <br/> |
   
Skype Empresarial Server 2015 usa internamente las tablas de la siguiente lista. Los detalles no se describen en este documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tablas para uso interno de Lync Server

|**Table**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Únicamente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Únicamente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla FrontEnd** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla MSMQProcessing** <br/> |Únicamente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla Syndicators** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla SyndicatorsTenantMap** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla Task** <br/> |Únicamente para uso interno.  <br/> |
|**UserStatistics** <br/> |Únicamente para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Únicamente para uso interno.  <br/> |
|**UsageSummary** <br/> |Únicamente para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Únicamente para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Únicamente para uso interno.  <br/> |
|**TimeZones** <br/> |Únicamente para uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Únicamente para uso interno.  <br/> |
|**FailureSummary** <br/> |Únicamente para uso interno.  <br/> |
|**ServerSummary** <br/> |Únicamente para uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Únicamente para uso interno.  <br/> |
   

