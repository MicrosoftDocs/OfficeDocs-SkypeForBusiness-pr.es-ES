---
title: Informe de diagnóstico en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Resumen: Información sobre el informe de diagnóstico en Skype para Business Server.'
ms.openlocfilehash: 15ef3d6e5663dee7ec0056ed48dc45119ad09db2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966387"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico en Skype para Business Server.
  
El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para las sesiones con errores. Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo el error en la sesión. El identificador de diagnóstico es un identificador único (con formato de encabezado ms-diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción que acompaña al identificador de diagnóstico. El informe también puede contener detalles valiosos sobre la solución de problemas conocidos por el componente del informe. Por ejemplo:
  
- El código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando una llamada saliente presenta errores en la red RTC, se genera automáticamente un código de causa ISUP (ISDN User Part). Por ejemplo, una puerta de enlace RTC puede enviar un código de causa 34 para indicar que no hay ningún canal o circuito disponible para completar la llamada.
    
- Errores de Winsock, puerto y FQDN del mismo nivel para detectar errores de conectividad.
    
- Comprobación de nombres para detectar errores de resolución DNS. La resolución DNS tiene lugar cada vez que un cliente establece contacto con un servidor de nombres y solicita la dirección IP correspondiente al nombre de dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Obtener acceso al informe de diagnóstico

El informe de diagnóstico puede tener acceso haciendo clic en la métrica informe de diagnósticos (detalle) en el [informe de detalles de la sesión de punto a punto en Skype para Business Server](peer-to-peer-session-detail-report.md) o el informe de detalles de conferencia.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.
  
## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información proporcionada en el informe de diagnóstico para cada sesión.
  
**Métricas del informe de diagnóstico**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora del informe** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Tipo de solicitud** <br/> |No  <br/> |Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE, BYE o SERVICE.  <br/> |
|**Origen** <br/> |No  <br/> |Origen del error.  <br/> |
|**URI de remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software usado por el extremo del usuario que inició la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tipo de contenido** <br/> |No  <br/> |Tipo de contenido multimedia que presentó errores. Un ejemplo de tipo de contenido habitual es Application/sdp. Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios e invitaciones de sesiones, y otras formas de iniciar sesiones multimedia.  <br/> |
|**Aplicación** <br/> |No  <br/> |Aplicación a la que corresponde el error.  <br/> |
|**URI de destinatario** <br/> |No  <br/> |Dirección SIP del usuario invitado a la sesión.  <br/> |
|**Tiempo en unirse a conferencia (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la conferencia.  <br/> |
|**Encabezado de diagnóstico** <br/> |No  <br/> |Descripción del identificador de diagnóstico.  <br/> |
   
Una lista de errores de diagnósticos puede encontrarse en la [página de encabezado Ms-Diagnostics](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).
  

