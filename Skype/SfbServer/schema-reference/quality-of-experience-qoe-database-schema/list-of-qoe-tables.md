---
title: Lista de tablas de QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: El esquema de base de datos consta de las siguientes tablas.
ms.openlocfilehash: 5f8957bfa4bbe2da75073082132468bff748c712
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-qoe-tables"></a>Lista de tablas de QoE
 
El esquema de base de datos consta de las siguientes tablas. 
  
**Tablas de soporte**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Almacena los valores óptimos y aceptables para las métricas de calidad de la experiencia usadas con uso compartido de aplicaciones.  <br/> |
|[Tabla CodecDescription](codecdescription.md) <br/> |Asigna identificadores de códec único a su códec correspondiente.  <br/> |
|[Tabla de dirección IP](ipaddress.md) <br/> |Asigna direcciones IP a los identificadores únicos de dirección IP utilizados en la base de datos de calidad de la experiencia.  <br/> |
|[Tabla NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Tipos de conexión de red se asigna a los identificadores de conexión de red utilizados en la base de datos de calidad de la experiencia.  <br/> |
|[Tabla PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Almacena información que especifica si (y cuándo) anticuados registros se eliminarán automáticamente de la base de datos de calidad de la experiencia de calidad de experiencia.  <br/> |
|[Tabla TraceRoute](traceroute.md) <br/> |Almacenes de información de enrutamiento de llamadas.  <br/> |
|[Tabla UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Asigna identificadores de agente de usuario a nombres descriptivos del agente.  <br/> |
|[Tabla VideoMetricsThreshold](videometricsthreshold.md) <br/> |Almacena los valores óptimos y aceptables para las métricas de calidad de la experiencia usadas con llamadas de vídeo.  <br/> |
|[Tabla UserAgent](useragent.md) <br/> |Almacena cadenas de agente de usuario de protocolo de inicio de sesión (SIP) (UA) y tipos UA utilizados en las sesiones de audio y vídeo.  <br/> |
|[Tabla de usuario](user-0.md) <br/> |Usuario de almacenes, conferencia y teléfono URI utilizan en sesiones de audio y vídeo.  <br/> |
|[Tabla de extremo](endpoint.md) <br/> |Almacena nombres FQDN de extremos que participen en las sesiones de audio y vídeo.  <br/> |
|[Mesa de billar](pool.md) <br/> |Almacena los nombres de los grupos a las métricas que pertenecen datos.  <br/> |
|[Tabla de dispositivos](device.md) <br/> |Almacenes de dispositivos de captura y representan los dispositivos que se utilizan en las llamadas de audio y vídeo.  <br/> |
|[Tabla DeviceDriver](devicedriver.md) <br/> |Almacena el controlador para el dispositivo de captura y el dispositivo de representación que se utilizan en las llamadas de audio y vídeo.  <br/> |
|[Mesa de conferencia](conference.md) <br/> |Almacena los URI de conferencia para escenarios de conferencia o DialogID para otros escenarios.  <br/> |
|[Tabla SessionCorrelation](sessioncorrelation.md) <br/> |Almacena CorrelationID para llamadas PSTN.  <br/> |
|[Tabla PayloadDescription](payloaddescription.md) <br/> |Almacena el códec que se utiliza en las llamadas de audio y vídeo.  <br/> |
|[Tabla AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Almacena el origen de ancho de banda utilizado en las llamadas de audio y vídeo.  <br/> |
|[Tabla de dirección MAC](macaddress.md) <br/> |Almacena la dirección MAC de los extremos que participen en las sesiones de audio y vídeo.  <br/> |
|[Cuadro de diálogo](dialog.md) <br/> |Almacena el identificador del cuadro de diálogo de las sesiones de audio y vídeo.  <br/> |
|[Tabla de región](region.md) <br/> |Almacena la región de red definida en configuración de NCS.  <br/> |
|[Tabla UserSite](usersite.md) <br/> |Almacena el sitio de red definido en configuración de NCS.  <br/> |
|[Tabla de subredes](subnet.md) <br/> |Almacena la subred definida en configuración de NCS.  <br/> |
|[Tabla MonitoredRegionLink](monitoredregionlink.md) <br/> |Almacena el vínculo de la región definido en la configuración de NCS.  <br/> |
|[Tabla MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Almacena los vínculos de sitio de red definidos en configuración de NCS.  <br/> |
|[Tabla EndpointSubnet](endpointsubnet.md) <br/> |Almacena la subred del extremo participando en una sesión de audio y vídeo.  <br/> |
|[Tabla de servidor](server.md) <br/> |Almacena las direcciones FQDN o IP del servidor que atraviesa el medio.  <br/> |
   
**Tablas de datos de métricas**

|**Tabla**|**Descripción**|
|:-----|:-----|
|[Tabla AppSharingStream](appsharingstream.md) <br/> |Almacena las métricas de calidad de la experiencia de las secuencias de red utilizadas para el uso compartido de aplicaciones. Calidad de métricas de experiencia para las secuencias de red utilizadas para el uso compartido de aplicaciones.  <br/> |
|[Tabla de sesiones](session.md) <br/> |Almacena información general sobre una sesión de audio o audio y vídeo. Una sesión se define como un cuadro de diálogo SIP de audio o vídeo entre dos extremos.  <br/> |
|[Tabla MediaLine](medialine-0.md) <br/> |Almacena información acerca de cada línea de medios en una sesión. Una línea de media es una colección de una o más secuencias de audio y vídeo. Normalmente, una línea de media solo tendrá dos secuencias, de audio o vídeo.  <br/> |
|[Tabla AudioStream](audiostream.md) <br/> |Almacena las métricas de calidad media audio para cada secuencia de audio en la línea media.  <br/> |
|[Tabla AudioSignal](audiosignal.md) <br/> |Almacena las métricas de calidad media audio en la línea media. Esto incluye la cancelación del eco acústico (AEC) y métricas de automatic gain control (AGC).  <br/> |
|[Tabla VideoStream](videostream.md) <br/> |Almacena las métricas de calidad de vídeo para cada secuencia de audio en la línea media.  <br/> |
|[Tabla AudioClientEvent](audioclientevent.md) <br/> |Métricas de calidad media audio almacenes recopilan desde el evento de cliente.  <br/> |
|[Tabla VideoClientEvent](videoclientevent.md) <br/> |Métrica de calidad de vídeo de almacenes recopilados desde el evento de cliente.  <br/> |
|**Tabla DiagnosticData** <br/> |Almacena datos de diagnóstico que es sólo para uso interno.  <br/> |
   
**Tablas de datos de resumen**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**Tabla ServerSummary** <br/> |Almacena datos de resumen para los servidores, estos datos se utilizan para la calidad de la experiencia (QoE) sólo informe.  <br/> |
|**Tabla UserSummary** <br/> |Almacena datos de resumen para los usuarios, estos datos se utilizan para QoE sólo informe.  <br/> |
|**Tabla CallTypeSummary** <br/> |Datos de resumen de almacén para los tipos de llamada, estos datos se utilizan para QoE sólo informe.  <br/> |
   
**Tablas para uso interno por el servidor de supervisión**

|**Tabla**|**Descripción**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Sólo para uso interno.  <br/> |
|**DbConfigInt** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de front-end** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de tareas** <br/> |Sólo para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Sólo para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Sólo para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Sólo para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Sólo para uso interno.  <br/> |
|**Zonas horarias** <br/> |Sólo para uso interno.  <br/> |
|**Tabla CallSummary** <br/> |Sólo para uso interno.  <br/> |
|**Tabla DeviceCallSumary** <br/> |Sólo para uso interno.  <br/> |
|**Tabla de inquilinos** <br/> |Sólo para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Sólo para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Sólo para uso interno.  <br/> |
   

