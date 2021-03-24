---
title: Informe de diagnóstico en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Resumen: obtenga información sobre el informe de diagnóstico en Skype Empresarial Server.'
ms.openlocfilehash: b7739214cf176336e47a5d2e11b36b52ea87eca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095244"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico en Skype Empresarial Server.
  
El informe de diagnóstico proporciona información de diagnóstico y solución de problemas para una sesión con errores. Esta información incluye tanto el identificador de diagnóstico como el encabezado Diagnóstico que se informaron cuando se ha registrado un error en la sesión. El identificador de diagnóstico es un identificador único (en forma de un encabezado ms-diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado Diagnóstico proporciona una descripción adjunta para el identificador de diagnóstico. El informe también puede contener detalles de solución de problemas valiosos conocidos por el componente de informes. Por ejemplo:
  
- Código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP). Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.
    
- Errores de FQDN, puerto y Winsock del mismo nivel para errores de conectividad.
    
- Nombres que se están buscando para los errores de resolución dns. La resolución dns tiene lugar cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre del dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Acceso al informe de diagnóstico

Para obtener acceso al informe de diagnóstico, haga clic en la métrica Informe de diagnóstico (detalle) en el Informe de detalles de sesión punto a punto en Skype Empresarial [Server](peer-to-peer-session-detail-report.md) o en el Informe de detalles de conferencia.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el Informe de diagnóstico para cada sesión.
  
**Métricas de informe de diagnóstico**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora del informe** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Tipo de solicitud** <br/> |No  <br/> |Tipo de solicitud SIP que ha fallado. Por ejemplo, INVITE, BYE o SERVICE.  <br/> |
|**Source** <br/> |No  <br/> |Origen del error.  <br/> |
|**URI de usuario** <br/> |No  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software que utiliza el extremo del usuario que inició la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.  <br/> |
|**Tipo de contenido** <br/> |No  <br/> |Tipo de contenido multimedia que ha fallado. Por ejemplo, un tipo de contenido común es Application/sdp. El Protocolo de descripción de sesión (SDP) es un protocolo de Internet estándar usado para anuncios de sesión, invitaciones de sesión y otras formas de inicio de sesión multimedia.  <br/> |
|**Aplicación** <br/> |No  <br/> |Aplicación implicada en el error.  <br/> |
|**Uri de usuario** <br/> |No  <br/> |Dirección SIP del usuario invitado a la sesión.  <br/> |
|**Horas de unión de conferencia (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la conferencia.  <br/> |
|**Encabezado de diagnóstico** <br/> |No  <br/> |Descripción del id. de diagnóstico.  <br/> |
   
Puede encontrar una lista de errores de diagnóstico en la [página Ms-Diagnostics Header](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3).
