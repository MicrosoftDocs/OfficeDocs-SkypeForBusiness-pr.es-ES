---
title: Informe detallado de sesión de punto a punto en Skype empresarial Server
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
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Resumen: Obtenga información sobre el informe de detalles de sesión de punto a punto en Skype empresarial Server.'
ms.openlocfilehash: 4c6b05e6e4e4110a43c21dbdbbc7f190ecae98ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817779"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Informe detallado de sesión de punto a punto en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de detalles de sesión de punto a punto en Skype empresarial Server.
  
El informe de detalles de sesiones punto a punto devuelve información detallada sobre una sesión punto a punto. Por ejemplo, si selecciona una sesión de mensajería instantánea, el informe reflejará la cantidad de mensajes enviados por cada usuario durante la sesión.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Acceso al informe de detalles de sesiones punto a punto

Se puede obtener acceso al informe de detalles de sesiones punto a punto desde cualquiera de los siguientes informes (todos se encuentran en la página principal de informes de supervisión):
  
- Informe de inventario de teléfono IP
    
- Informe de actividad de usuario
    
- Informe de control de admisión de llamadas
    
- Informe de lista de errores 
    
Desde dentro del informe detallado de sesión de punto a punto, puede acceder al [Informe de diagnóstico en Skype empresarial Server](diagnostic-report.md) haciendo clic en la métrica de informe de diagnóstico (detalles). También se puede obtener acceso al informe de errores principales haciendo clic en cualquiera de estas dos métricas:
  
- Respuesta
    
- Id. de diagnóstico
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Usar el informe de detalles de sesiones punto a punto de la mejor forma posible

El informe de detalles de sesiones punto a punto condensa un gran número de métricas, de las cuales probablemente muchas no sean muy conocidas para los administradores de sistema. Pero, muchas veces se puede obtener acceso a información sobre herramientas en la que se ofrece una breve descripción de la métrica; para ello, basta con mantener el mouse encima de la etiqueta de la métrica.
  
Recuerde que las métricas reales que aparecen reflejadas en un informe determinado dependerán del tipo de sesión punto a punto seleccionado. Así, las métricas de una sesión de audio/vídeo serán distintas de las de una sesión de mensajería instantánea.
  
El mouse también se puede mantener sobre las métricas Código de respuesta e Id. de diagnóstico para obtener una descripción de dichos valores:
  
## <a name="filters"></a>Filtros

Ninguno. El informe de detalles de sesiones punto a punto no se puede filtrar.
  
## <a name="session-information-metrics"></a>Métricas de información de la sesión

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada sesión.
  
**Métricas de información de la sesión**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**FQDN del grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registrador o servidor perimetral involucrado en la sesión.  <br/> |
|**Hora de invitación** <br/> |Fecha y hora en que se envió inicialmente la invitación a la sesión.  <br/> |
|**Tiempo de respuesta** <br/> |Fecha y hora en que se recibió la aceptación de la invitación.  <br/> |
|**Remitente** <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Agente de remitente** <br/> |Software usado por el extremo del usuario que inició la sesión.  <br/> |
|**¿Es el remitente interno?** <br/> |Indica si el usuario que inició la sesión estaba conectado a la red interna.  <br/> |
|**¿Tiene el remitente un teléfono de escritorio integrado?** <br/> |Indica si el extremo que utilizó el usuario que inició sesión está integrado en su teléfono de escritorio integrado.  <br/> |
|**Prioridad de sesión** <br/> |Prioridad asignada a la sesión. Entre las propiedades válidas se encuentran Desconocido, No urgente, Normal, Urgente y Emergencia.  <br/> |
|**Código de respuesta** <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Front-end** <br/> |Nombre del servidor front-end que se usó en la conferencia.  <br/> |
|**Hora de captura** <br/> |Fecha y hora en que se registró la información de la sesión.  <br/> |
|**Hora de finalización** <br/> |Fecha y hora en que la sesión finalizó.  <br/> |
|**Destinatario** <br/> |Dirección SIP del usuario invitado a la sesión.  <br/> |
|**Agente de destinatario** <br/> |Software utilizado por el extremo del usuario invitado a la sesión.  <br/> |
|**¿Es el destinatario interno?** <br/> |Indica si el usuario invitado a la sesión estaba conectado a la red interna.  <br/> |
|**¿Tiene el destinatario un teléfono de escritorio integrado?** <br/> |Indica si el extremo que utilizó el usuario invitado a la sesión está integrado en su teléfono de escritorio integrado.  <br/> |
|**¿Es un reintento de sesión?** <br/> |Indica si se trata de un reintento de una sesión que no se pudo iniciar correctamente.  <br/> |
|**Id. de diagnóstico** <br/> |Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores. Mantenga el mouse encima del número del identificador para ver más información al respecto.  <br/> |
   
## <a name="metrics-for-modalities"></a>Métricas de modalidades

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada modalidad de sesión.
  
**Métricas de modalidades**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Modalidades** <br/> |No  <br/> |Modalidades usadas en la sesión (por ejemplo, mensajería instantánea o transferencia de archivos).  <br/> |
|**Mensajes del remitente** <br/> |No  <br/> |Cantidad de mensajes que envió el usuario que inició la sesión.  <br/> |
|**Mensajes del destinatario** <br/> |No  <br/> |Cantidad de mensajes que envió el usuario invitado a unirse a la sesión.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Métricas de informes de diagnóstico

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada informe de diagnóstico.
  
**Métricas de informes de diagnóstico**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Detalle** <br/> |No  <br/> |Cuando se hace clic en este elemento, el informe muestra el informe de diagnóstico correspondiente a la sesión.  <br/> |
|**Hora del informe** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Solicitud** <br/> |No  <br/> |Tipo de solicitud SIP (por ejemplo, INVITE o BYE).  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tipo de contenido** <br/> |No  <br/> |Tipo de contenido multimedia usado en la conferencia (por ejemplo, un tipo de contenido bastante habitual es Application/sdp). El protocolo SDP es un protocolo de Internet estándar que se usa en anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesiones multimedia.  <br/> |
|**Informe realizado por** <br/> |No  <br/> |Equipo (cliente o servidor) que notificó el problema.  <br/> |
   

