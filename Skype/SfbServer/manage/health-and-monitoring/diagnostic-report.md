---
title: Informe de diagnósticos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Resumen: Obtenga información sobre el informe de diagnóstico en Skype empresarial Server.'
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041997"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Informe de diagnósticos en Skype empresarial Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico en Skype empresarial Server.
  
El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para una sesión con error. Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo un error en la sesión. El identificador de diagnóstico es un identificador único (en forma de un encabezado MS-Diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción complementaria del identificador de diagnóstico. El informe también puede contener detalles de solución de problemas valiosos que el componente de informes conoce. Por ejemplo:
  
- El código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP). Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.
    
- Errores de conectividad, puerto y FQDN del mismo nivel para errores de conectividad.
    
- Nombres que se buscan en busca de errores de resolución DNS. La resolución DNS tiene su comportamiento cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre de dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Acceso al informe de diagnósticos

Para obtener acceso al informe de diagnóstico, haga clic en la métrica informe de diagnóstico (detalle) en el [Informe de detalles de sesiones punto a punto de Skype empresarial Server](peer-to-peer-session-detail-report.md) o en el informe de detalles de conferencia.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.
  
## <a name="metrics"></a>Métricas

En la siguiente tabla se muestra la información proporcionada en el informe de diagnóstico para cada sesión.
  
**Métricas del informe de diagnóstico**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora del informe** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Tipo de solicitud** <br/> |No  <br/> |Tipo de solicitud SIP fallida. Por ejemplo, INVITE, BYE o SERVICE.  <br/> |
|**Source** <br/> |No  <br/> |Origen del error.  <br/> |
|**URI de usuario de remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software que utiliza el extremo del usuario que inició la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.  <br/> |
|**Tipo de contenido** <br/> |No  <br/> |Tipo de contenido multimedia con errores. Por ejemplo, un tipo de contenido común es Application/SDP. Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesión multimedia.  <br/> |
|**Application** <br/> |No  <br/> |Aplicación implicada en el error.  <br/> |
|**URI de usuario** <br/> |No  <br/> |Dirección SIP del usuario invitado a la sesión.  <br/> |
|**Tiempos de combinación de conferencia (MS)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la Conferencia.  <br/> |
|**Encabezado de diagnóstico** <br/> |No  <br/> |Descripción del identificador de diagnóstico.  <br/> |
   
Se puede encontrar una lista de errores de diagnóstico en la [Página de encabezado de MS-Diagnostics](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx).
  

