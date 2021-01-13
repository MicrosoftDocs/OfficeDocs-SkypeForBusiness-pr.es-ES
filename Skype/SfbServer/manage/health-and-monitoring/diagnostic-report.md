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
ms.openlocfilehash: 89639c0c00081fa4dd01211cc33074585061ff57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816900"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico en Skype Empresarial Server.
  
El informe de diagnóstico proporciona información de diagnóstico y solución de problemas para una sesión con errores. Esta información incluye tanto el identificador de diagnóstico como el encabezado de diagnóstico que se han notificado cuando se ha fallado la sesión. El id. de diagnóstico es un identificador único (en forma de un encabezado ms-diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción adjunta para el id. de diagnóstico. El informe también puede contener valiosos detalles de solución de problemas conocidos por el componente de informes. Por ejemplo:
  
- Código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP). Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.
    
- Errores de FQDN, puerto y Winsock del mismo nivel para errores de conectividad.
    
- Nombres que se están buscando para los errores de resolución DNS. La resolución DNS tiene lugar cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre de dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Acceso al informe de diagnóstico

Para obtener acceso al informe de diagnóstico, haga clic en la métrica Informe de diagnóstico (detalles) en el informe de detalles de sesiones punto a punto en Skype Empresarial [Server](peer-to-peer-session-detail-report.md) o en el informe de detalles de conferencia.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el Informe de diagnóstico para cada sesión.
  
**Métricas del informe de diagnóstico**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora del informe** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Tipo de solicitud** <br/> |No  <br/> |Tipo de solicitud SIP con error. Por ejemplo, INVITE, BYE o SERVICE.  <br/> |
|**Source** <br/> |No  <br/> |Origen del error.  <br/> |
|**URI del usuario** <br/> |No  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software que utiliza el extremo del usuario que inició la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.  <br/> |
|**Tipo de contenido** <br/> |No  <br/> |Tipo de contenido multimedia que ha fallado. Por ejemplo, un tipo de contenido común es Application/sdp. El Protocolo de descripción de sesión (SDP) es un protocolo estándar de Internet que se usa para anuncios de sesión, invitaciones a sesiones y otras formas de inicio de sesión multimedia.  <br/> |
|**Aplicación** <br/> |No  <br/> |Aplicación implicada en el error.  <br/> |
|**URI de usuario** <br/> |No  <br/> |Dirección SIP del usuario invitado a la sesión.  <br/> |
|**Horas de participación en conferencias (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la conferencia.  <br/> |
|**Encabezado de diagnóstico** <br/> |No  <br/> |Descripción del id. de diagnóstico.  <br/> |
   
Puede encontrar una lista de errores de diagnóstico en la [página Ms-Diagnostics Header](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx).
  

