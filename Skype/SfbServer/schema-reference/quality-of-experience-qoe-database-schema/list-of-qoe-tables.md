---
title: Lista de tablas de QoE
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: El esquema de la base de datos incluye las tablas siguientes.
ms.openlocfilehash: 291d2ddefefc264aa283480362a6f57cda9161cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834490"
---
# <a name="list-of-qoe-tables"></a>Lista de tablas de QoE
 
El esquema de la base de datos incluye las tablas siguientes. 
  
**Tablas auxiliares**

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa al compartir aplicaciones.  <br/> |
|[Tabla CodecDescription](codecdescription.md) <br/> |Asigna identificadores de códecs únicos al códec correspondiente.  <br/> |
|[Tabla IPAddress](ipaddress.md) <br/> |Asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de Calidad de la experiencia.  <br/> |
|[Tabla NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de Calidad de la experiencia.  <br/> |
|[Tabla PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Almacena información que especifica si los registros de Calidad de la experiencia no actualizados se eliminarán automáticamente de la base de datos de QoE (así como cuándo se eliminarán).  <br/> |
|[Tabla TraceRoute](traceroute.md) <br/> |Almacena la información de enrutamiento de las llamadas.  <br/> |
|[Tabla UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Asigna identificadores de agente de usuario a los nombres descriptivos del agente.  <br/> |
|[Tabla VideoMetricsThreshold](videometricsthreshold.md) <br/> |Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa con las llamadas de vídeo.  <br/> |
|[Tabla UserAgent](useragent.md) <br/> |Almacena las cadenas del agente de usuario del Protocolo de inicio de sesión (SIP) y los tipos de agentes de usuario utilizados en las sesiones de audio y vídeo.  <br/> |
|[Tabla User](user-0.md) <br/> |Almacena los URI de teléfono, usuario y conferencia utilizados en las sesiones de audio y vídeo.  <br/> |
|[Tabla Endpoint](endpoint.md) <br/> |Almacena los nombres de equipo FQDN de los extremos que participan en las sesiones de audio y vídeo.  <br/> |
|[Tabla Pool](pool.md) <br/> |Almacena los nombres de los grupos de servidores a los que pertenecen los datos de métricas.  <br/> |
|[Tabla Device](device.md) <br/> |Almacena los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.  <br/> |
|[Tabla DeviceDriver](devicedriver.md) <br/> |Almacena el controlador de los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.  <br/> |
|[Tabla Conference](conference.md) <br/> |Almacena los URI de conferencia para los escenarios de conferencia o el identificador de diálogo para otros escenarios.  <br/> |
|[Tabla SessionCorrelation](sessioncorrelation.md) <br/> |Almacena el identificador de correlación de las llamadas RTC.  <br/> |
|[Tabla PayloadDescription](payloaddescription.md) <br/> |Almacena el códec utilizado en las llamadas de audio/vídeo.  <br/> |
|[Tabla AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Almacena el origen de ancho de banda utilizado en las llamadas de audio/vídeo.  <br/> |
|[Tabla MacAddress](macaddress.md) <br/> |Almacena la dirección MAC de los extremos que participan en las sesiones de audio y vídeo.  <br/> |
|[Tabla dialog](dialog.md) <br/> |Almacena el identificador de diálogo de las sesiones de audio y vídeo.  <br/> |
|[Tabla Region](region.md) <br/> |Almacena la región de red definida en la configuración NCS.  <br/> |
|[Tabla UserSite](usersite.md) <br/> |Almacena el sitio de red definido en la configuración NCS.  <br/> |
|[Tabla Subnet](subnet.md) <br/> |Almacena la subred definida en la configuración NCS.  <br/> |
|[Tabla MonitoredRegionLink](monitoredregionlink.md) <br/> |Almacena el vínculo de región definido en la configuración NCS.  <br/> |
|[Tabla MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Almacena los vínculos de sitios de red definidos en la configuración NCS.  <br/> |
|[Tabla EndpointSubnet](endpointsubnet.md) <br/> |Almacena la subred del extremo que participa en las sesiones de audio y vídeo.  <br/> |
|[Tabla Server](server.md) <br/> |Almacena el FQDN o la dirección IP del servidor que utilizan los medios.  <br/> |
   
**Tablas para datos de métricas**

|**Table**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingStream](appsharingstream.md) <br/> |Almacena las métricas de Calidad de la experiencia para los flujos de red usados al compartir aplicaciones. Las métricas de calidad de la experiencia se usan al compartir aplicaciones.  <br/> |
|[Tabla Session](session.md) <br/> |Almacena información general acerca de una sesión de audio o de audio/vídeo. Una sesión se define como un diálogo SIP de audio o vídeo entre dos extremos.  <br/> |
|[Tabla MediaLine](medialine-0.md) <br/> |Almacena información acerca de cada línea de medios de una sesión. Una línea de medios es una recopilación de una o varias secuencias de audio y vídeo. Por lo general, una única línea de medios tendrá dos secuencias, de audio o de vídeo.  <br/> |
|[Tabla AudioStream](audiostream.md) <br/> |Almacena métricas de calidad de medios de audio para cada secuencia de audio de la línea de medios.  <br/> |
|[Tabla AudioSignal](audiosignal.md) <br/> |Almacena métricas de calidad de medios de audio de la línea de medios. Esto incluye las métricas de cancelación del eco acústico (AEC) y el control de ganancia automático (AGC).  <br/> |
|[Tabla VideoStream](videostream.md) <br/> |Almacena métricas de calidad de medios de vídeo para cada secuencia de vídeo de la línea de medios.  <br/> |
|[Tabla AudioClientEvent](audioclientevent.md) <br/> |Almacena métricas de calidad de medios de audio recopiladas desde el evento del cliente.  <br/> |
|[Tabla VideoClientEvent](videoclientevent.md) <br/> |Almacena métricas de calidad de medios de vídeo recopiladas desde el evento del cliente.  <br/> |
|**Tabla DiagnosticData** <br/> |Almacena datos de diagnóstico para uso interno únicamente.  <br/> |
   
**Tablas para datos de resumen**

|**Table**|**Descripción**|
|:-----|:-----|
|**Tabla ServerSummary** <br/> |Almacena datos de resumen para los servidores; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.  <br/> |
|**Tabla UserSummary** <br/> |Almacena datos de resumen para los usuarios; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.  <br/> |
|**Tabla CallTypeSummary** <br/> |Almacena datos de resumen para los tipos de llamada; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.  <br/> |
   
**Tablas para uso interno del servidor de supervisión**

|**Table**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Únicamente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla FrontEnd** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla Task** <br/> |Únicamente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Únicamente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Únicamente para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Únicamente para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Únicamente para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Únicamente para uso interno.  <br/> |
|**TimeZones** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla CallSummary** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla DeviceCallSumary** <br/> |Únicamente para uso interno.  <br/> |
|**Tabla Tenant** <br/> |Únicamente para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Únicamente para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Únicamente para uso interno.  <br/> |
   

