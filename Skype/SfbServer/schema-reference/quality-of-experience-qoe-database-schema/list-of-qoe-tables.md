---
title: Lista de tablas de QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: El esquema de la base de datos consta de las siguientes tablas.
ms.openlocfilehash: 6c82585195befda13ebb14215e72a59341fac1d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809008"
---
# <a name="list-of-qoe-tables"></a>Lista de tablas de QoE
 
El esquema de la base de datos consta de las siguientes tablas. 
  
**Tablas de soporte técnico**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones.  <br/> |
|[Tabla CodecDescription](codecdescription.md) <br/> |Asigna identificadores de códec únicos a su códec correspondiente.  <br/> |
|[Tabla dirección IP](ipaddress.md) <br/> |Asigna direcciones IP a los identificadores de dirección IP única que se usan en otras partes de la base de datos de la calidad de la experiencia.  <br/> |
|[Tabla NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mapas tipos de conexión de red a los identificadores de conexión de red usados en otras partes de la base de datos de la calidad de la experiencia.  <br/> |
|[Tabla PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Almacena información que especifica si (y cuándo) la calidad de los registros de experiencia se eliminará automáticamente de la base de datos de QoE.  <br/> |
|[Tabla TraceRoute](traceroute.md) <br/> |Almacena la información de enrutamiento de las llamadas.  <br/> |
|[Tabla UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla VideoMetricsThreshold](videometricsthreshold.md) <br/> |Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con las videollamadas.  <br/> |
|[Tabla UserAgent](useragent.md) <br/> |Almacena las cadenas y los tipos de UA del agente de usuario del Protocolo de inicio de sesión (SIP) que se usan en sesiones de audio y vídeo.  <br/> |
|[Tabla User](user-0.md) <br/> |Almacena los URI de usuario, Conferencia y teléfono que se usan en las sesiones de audio y vídeo.  <br/> |
|[Tabla Endpoint](endpoint.md) <br/> |Almacena FQDN de los nombres de los equipos de puntos de conexión que participan en sesiones de audio y vídeo.  <br/> |
|[Tabla Pool](pool.md) <br/> |Almacena los nombres de los grupos a los que pertenecen los datos de métrica.  <br/> |
|[Tabla Device](device.md) <br/> |Almacena dispositivos de captura y dispositivos de representación que se usan en una llamada de audio o vídeo.  <br/> |
|[Tabla DeviceDriver](devicedriver.md) <br/> |Almacena el controlador para el dispositivo de captura y el dispositivo de representación que se usan en las llamadas de audio o vídeo.  <br/> |
|[Tabla Conference](conference.md) <br/> |Almacena los URI de conferencia para escenarios de conferencia o DialogID para otros escenarios.  <br/> |
|[Tabla SessionCorrelation](sessioncorrelation.md) <br/> |Almacena CorrelationID para llamadas RTC.  <br/> |
|[Tabla PayloadDescription](payloaddescription.md) <br/> |Almacena el códec usado en las llamadas de audio o vídeo.  <br/> |
|[Tabla AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Almacena la fuente de ancho de banda que se usa en las llamadas de audio o vídeo.  <br/> |
|[Tabla MacAddress](macaddress.md) <br/> |Almacena la dirección MAC de los puntos de conexión que participan en sesiones de audio y vídeo.  <br/> |
|[Tabla Dialog](dialog.md) <br/> |Almacena el identificador de cuadro de diálogo de las sesiones de audio y vídeo.  <br/> |
|[Tabla Region](region.md) <br/> |Almacena la región de red definida en NC.  <br/> |
|[Tabla UserSite](usersite.md) <br/> |Almacena el sitio de red definido en NC Settings.  <br/> |
|[Tabla Subnet](subnet.md) <br/> |Almacena la subred definida en la configuración de NC.  <br/> |
|[Tabla MonitoredRegionLink](monitoredregionlink.md) <br/> |Almacena el vínculo región definido en NC.  <br/> |
|[Tabla MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Almacena los vínculos de sitio de red definidos en NC.  <br/> |
|[Tabla EndpointSubnet](endpointsubnet.md) <br/> |Almacena la subred del punto final que participa en una sesión de audio y vídeo.  <br/> |
|[Tabla Server](server.md) <br/> |Almacena el FQDN o la dirección IP del servidor en el que se recorren los medios.  <br/> |
   
**Tablas para datos de métricas**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingStream](appsharingstream.md) <br/> |Almacena métricas de experiencia de evaluación de la calidad de las secuencias de red usadas para compartir aplicaciones. Métricas de la calidad de la experiencia de las secuencias de red que se usan para compartir aplicaciones.  <br/> |
|[Tabla Session](session.md) <br/> |Almacena información general sobre una sesión de audio o vídeo o audio. Una sesión se define como un cuadro de diálogo SIP de audio o vídeo entre dos puntos finales.  <br/> |
|[Tabla MediaLine](medialine-0.md) <br/> |Almacena información sobre cada línea multimedia de una sesión. Una línea de medios es una colección de una o más secuencias de audio y vídeo. Normalmente, una única línea multimedia tendrá dos secuencias, ya sea audio o vídeo.  <br/> |
|[Tabla AudioStream](audiostream.md) <br/> |Almacena las métricas de calidad de audio multimedia de audio de cada flujo de audio de la línea de medios.  <br/> |
|[Tabla AudioSignal](audiosignal.md) <br/> |Almacena las métricas de calidad de audio multimedia en la línea media. Esto incluye la métrica de cancelación de eco acústico (AEC) y las métricas de control automático de ganancia (AGC).  <br/> |
|[Tabla VideoStream](videostream.md) <br/> |Almacena métricas de calidad de medios de vídeo para cada flujo de audio de la línea de medios.  <br/> |
|[Tabla AudioClientEvent](audioclientevent.md) <br/> |Almacena las métricas de calidad de audio multimedia recopiladas del evento de cliente.  <br/> |
|[Tabla VideoClientEvent](videoclientevent.md) <br/> |Almacena las métricas de calidad de medios de vídeo recopiladas desde el evento de cliente.  <br/> |
|**Tabla DiagnosticData** <br/> |Almacena datos de diagnóstico que solo son para uso interno.  <br/> |
   
**Tablas de datos de Resumen**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**Tabla ServerSummary** <br/> |Almacena los datos de Resumen de los servidores, estos datos se usan únicamente para los informes de calidad de la experiencia (QoE).  <br/> |
|**Tabla UserSummary** <br/> |Almacena los datos de Resumen de los usuarios, estos datos se usan solo para informes de QoE.  <br/> |
|**Tabla CallTypeSummary** <br/> |Almacenar datos de Resumen de tipos de llamadas: estos datos se usan para informes de QoE únicamente.  <br/> |
   
**Tablas para uso interno mediante el servidor de supervisión**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Solo para uso interno.  <br/> |
|**Tabla de FrontEnd** <br/> |Solo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Solo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Solo para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Solo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo para uso interno.  <br/> |
|**TimeZones** <br/> |Solo para uso interno.  <br/> |
|**Tabla CallSummary** <br/> |Solo para uso interno.  <br/> |
|**Tabla DeviceCallSumary** <br/> |Solo para uso interno.  <br/> |
|**Tabla de inquilinos** <br/> |Solo para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Solo para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Solo para uso interno.  <br/> |
   

