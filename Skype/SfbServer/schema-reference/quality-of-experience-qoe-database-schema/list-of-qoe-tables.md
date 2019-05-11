---
title: Lista de tablas de QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: El esquema de base de datos consta de las siguientes tablas.
ms.openlocfilehash: e3e4ecb565e5a3a2f51d29ac77d4f1e87f3bf8eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920085"
---
# <a name="list-of-qoe-tables"></a>Lista de tablas de QoE
 
El esquema de base de datos consta de las siguientes tablas. 
  
**Tablas auxiliares**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Almacena los valores aceptables y óptimos para la métrica de calidad de la experiencia que se usa con el uso compartido de aplicaciones.  <br/> |
|[Tabla CodecDescription](codecdescription.md) <br/> |Asigna identificadores de códecs únicos al códec correspondiente.  <br/> |
|[Tabla IPAddress](ipaddress.md) <br/> |Asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de calidad de la experiencia.  <br/> |
|[Tabla NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Asigna los tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de calidad de la experiencia.  <br/> |
|[Tabla PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Almacena información que especifica si (y cuando) obsoletos registros se eliminarán automáticamente de la base de datos de calidad de la experiencia de calidad de experiencia.  <br/> |
|[Tabla TraceRoute](traceroute.md) <br/> |Almacenes de información de enrutamiento de llamadas.  <br/> |
|[Tabla UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla VideoMetricsThreshold](videometricsthreshold.md) <br/> |Almacena los valores aceptables y óptimos para la métrica de calidad de la experiencia que se usa con llamadas de vídeo.  <br/> |
|[Tabla UserAgent](useragent.md) <br/> |Almacena las cadenas de agente de usuario de protocolo de inicio de sesión (SIP) (UA) y tipos UA utilizados en las sesiones de audio y vídeos.  <br/> |
|[Tabla User](user-0.md) <br/> |Usuario de almacenes, conferencia y URI de teléfono utilizan en las sesiones de audio y vídeos.  <br/> |
|[Tabla Endpoint](endpoint.md) <br/> |Almacena los nombres de equipo FQDN de los extremos que participan en sesiones de audio y vídeo.  <br/> |
|[Tabla Pool](pool.md) <br/> |Almacena los nombres de los grupos de servidores para las métricas que pertenecen datos.  <br/> |
|[Tabla Device](device.md) <br/> |Almacena los dispositivos de captura y representar los dispositivos que se usan en las llamadas de audio y vídeo.  <br/> |
|[Tabla DeviceDriver](devicedriver.md) <br/> |Almacena el controlador para el dispositivo de captura y el dispositivo de presentación que se usan en las llamadas de audio y vídeo.  <br/> |
|[Tabla Conference](conference.md) <br/> |Almacena los URI de conferencia para escenarios de conferencia o DialogID para otros escenarios.  <br/> |
|[Tabla SessionCorrelation](sessioncorrelation.md) <br/> |Almacena CorrelationID para las llamadas de RTC.  <br/> |
|[Tabla PayloadDescription](payloaddescription.md) <br/> |Almacena el códec utilizado en las llamadas de audio y vídeo.  <br/> |
|[Tabla AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Almacena el origen de ancho de banda utilizado en las llamadas de audio y vídeo.  <br/> |
|[Tabla MacAddress](macaddress.md) <br/> |Almacena la dirección MAC de los extremos que participan en sesiones de audio y vídeo.  <br/> |
|[Tabla Dialog](dialog.md) <br/> |Almacena el identificador de diálogo de sesiones de audio y vídeo.  <br/> |
|[Tabla Region](region.md) <br/> |Almacena la región de red definida en la configuración NCS.  <br/> |
|[Tabla UserSite](usersite.md) <br/> |Almacena el sitio de red definido en la configuración NCS.  <br/> |
|[Tabla Subnet](subnet.md) <br/> |Almacena la subred definida en la configuración NCS.  <br/> |
|[Tabla MonitoredRegionLink](monitoredregionlink.md) <br/> |Almacena el vínculo de región definido en la configuración NCS.  <br/> |
|[Tabla MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Almacena los vínculos de sitio de red definidos en la configuración NCS.  <br/> |
|[Tabla EndpointSubnet](endpointsubnet.md) <br/> |Almacena la subred del extremo que participa en una sesión de audio y vídeo.  <br/> |
|[Tabla Server](server.md) <br/> |Almacena el FQDN o la dirección IP del servidor que utilizan los medios.  <br/> |
   
**Tablas para datos de métricas**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingStream](appsharingstream.md) <br/> |Almacena métricas de calidad de la experiencia de las secuencias de red usadas para uso compartido de aplicaciones. Calidad de métricas de experiencia para las secuencias de red usadas para uso compartido de aplicaciones.  <br/> |
|[Tabla Session](session.md) <br/> |Almacena información general acerca de una sesión de audio o audio y vídeo. Una sesión se define como un cuadro de diálogo SIP de audio o vídeo entre dos extremos.  <br/> |
|[Tabla MediaLine](medialine-0.md) <br/> |Almacena información acerca de cada línea de medios en una sesión. Una línea de medios es una colección de una o varias secuencias de audio y vídeos. Normalmente, una línea de medios solo tendrá dos secuencias, audio o vídeos.  <br/> |
|[Tabla AudioStream](audiostream.md) <br/> |Almacena métricas de calidad de medios de audio para cada secuencia de audio en la línea de medios.  <br/> |
|[Tabla AudioSignal](audiosignal.md) <br/> |Almacena métricas de calidad de medios de audio en la línea de medios. Esto incluye la cancelación del eco acústico (AEC) y métricas de ganancia automático (AGC) del control.  <br/> |
|[Tabla VideoStream](videostream.md) <br/> |Almacena métricas de calidad de medios de vídeo para cada secuencia de audio en la línea de medios.  <br/> |
|[Tabla AudioClientEvent](audioclientevent.md) <br/> |Almacena métricas de calidad de medios de audio recopilan desde el evento de cliente.  <br/> |
|[Tabla VideoClientEvent](videoclientevent.md) <br/> |Almacena métricas de calidad de medios de vídeo recopilan desde el evento de cliente.  <br/> |
|**Tabla DiagnosticData** <br/> |Almacena datos de diagnóstico que es sólo para uso interno.  <br/> |
   
**Tablas de datos de resumen**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**Tabla ServerSummary** <br/> |Almacena datos de resumen para los servidores, estos datos se usan para la calidad de la experiencia (QoE) solo de informes.  <br/> |
|**Tabla UserSummary** <br/> |Almacena datos de resumen para los usuarios, estos datos se usan para QoE sólo de informes.  <br/> |
|**Tabla CallTypeSummary** <br/> |Almacena datos de resumen para los tipos de llamada, estos datos se usan para QoE sólo de informes.  <br/> |
   
**Tablas para uso interno del servidor de supervisión**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Sólo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Sólo para uso interno.  <br/> |
|**Tabla FrontEnd** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Sólo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Sólo para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Sólo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Sólo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**TimeZones** <br/> |Sólo para uso interno.  <br/> |
|**Tabla CallSummary** <br/> |Sólo para uso interno.  <br/> |
|**Tabla DeviceCallSumary** <br/> |Sólo para uso interno.  <br/> |
|**Tabla tenant** <br/> |Sólo para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Sólo para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Sólo para uso interno.  <br/> |
   

