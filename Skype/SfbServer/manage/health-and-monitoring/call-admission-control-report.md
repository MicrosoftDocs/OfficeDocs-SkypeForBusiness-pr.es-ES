---
title: Informe del servicio de control de admisión de llamadas en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Resumen: Conozca los informes de Control de admisión de llamar utilizado en Skype para Business Server 2015.'
ms.openlocfilehash: 53c3767ad93b7faa4c7f9a7f33213dde21dd7ca5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-report-in-skype-for-business-server-2015"></a>Informe del servicio de control de admisión de llamadas en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca de los informes de Control de admisión de llamar utilizado en Skype para Business Server 2015.
  
El Informe de control de admisión de llamadas ofrece información sobre las sesiones de punto a punto y de conferencia que se han llevado a cabo con restricciones definidas por el Control de admisión de llamadas. El Control de admisión de llamadas proporciona a los administradores la forma de permitir (o no) las sesiones de comunicación en función de las restricciones del ancho de banda. Por ejemplo, los administradores pueden crear directivas que impongan un límite a la cantidad de ancho de banda disponible para las llamadas de voz y vídeo. Si se alcanza ese límite de ancho de banda, no se podrán realizar nuevas llamadas de voz o vídeo hasta que finalice alguna de las llamadas en curso y se liberen los recursos de red necesarios.
  
## <a name="accessing-the-call-admission-control-report"></a>Acceso al Informe de control de admisión de llamadas

Al Informe de control de admisión de llamadas se obtiene acceso desde la página de inicio de Informes de supervisión. Desde el Informe de control de admisión de llamadas, puede obtener acceso a cualquiera de los informes siguientes:
  
- Informe de detalle de conferencia: para acceder a este informe, haga clic en la métrica de detalles de una sesión de conferencia. 
    
- Peer-to-Peer sesión detalle informe: para tener acceso a este informe, haga clic en la métrica de detalles para una sesión de peer-to-peer.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Cómo hacer el mejor uso del Informe de control de admisión de llamadas

Para obtener una lista de las llamadas que no se han podido completar correctamente porque el ancho de banda no era suficiente, seleccione Llamadas rechazadas por el control de admisión de llamadas en la lista desplegable Categoría de llamada. La mayoría de las llamadas devueltas presentarán seguramente el identificador de diagnóstico 5:
  
Ancho de banda insuficiente para establecer la sesión. Intente volver a enrutar la llamada a través de RTC.
  
Este mensaje indica que las limitaciones del Control de admisión de llamadas impidió que la llamada se realizara en la red VoIP.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de control de admisión de llamadas le permite filtrar llamadas por el usuario que inicia la llamada o por el usuario que recibe la llamada. También puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de control de admisión de llamadas.
  
**Llamar a filtros de informe de Control de admisión**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Tipo de actividad** <br/> | Tipo de actividad. Seleccione una de las siguientes actividades: <br/>  [Todas] <br/>  Punto a punto <br/>  Una conferencia <br/> |
|**Categoría de llamada** <br/> | Indica el motivo por el que se usó el control de admisión de llamadas para la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Llamada rechazada por el control de admisión de llamadas <br/>  Llamadas que se han vuelto a enrutar a través de RTC por el control de admisión de llamadas <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información proporcionada por el Informe del control de admisión de llamadas para las sesiones punto a punto (es decir, sesiones entre solo dos participantes).
  
**Métricas para la sesiones de Peer-to-Peer**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Detalle** <br/> |No  <br/> |Cuando se hace clic en este elemento, el informe muestra un informe detallado de sesión punto a punto de la sesión específica.  <br/> |
|**Remitente** <br/> |Sí  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Destinatario** <br/> |Sí  <br/> |Dirección SIP del usuario al que se invitó a unirse a la sesión.  <br/> |
|**Modalidades** <br/> |Sí  <br/> |Modalidades de comunicación (como audio y vídeo) que se usaron durante la sesión.  <br/> |
|**Hora de invitación** <br/> |Sí  <br/> |Fecha y hora en que se envió al remitente la invitación a la sesión inicial.  <br/> |
|**Tiempo de respuesta** <br/> |Sí  <br/> |Fecha y hora en que se recibió la aceptación de la invitación.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en que finalizó la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |Sí  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra información proporcionada en el Informe de control de admisión de llamadas para las sesiones de conferencia (es decir, sesiones con tres o más participantes).
  
**Métricas para la sesiones de conferencia**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**URI de conferencia** <br/> |Sí  <br/> |Identificador único de la conferencia. Cuando se hace clic en este elemento, el informe muestra los participantes individuales de la conferencia.  <br/> |
|**Organizador** <br/> |Sí  <br/> |Dirección SIP del usuario que organizó la conferencia  <br/> |
|**Grupo de servidores** <br/> |Sí  <br/> |Servidor perimetral usado en la conferencia.  <br/> |
|**Hora de inicio** <br/> |Sí  <br/> |Fecha y hora en que comenzó la conferencia.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en que la conferencia finalizó.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Métricas de participantes en conferencias individuales

En la siguiente tabla se muestra la información proporcionada en el Informe de control de admisión de llamadas sobre participantes en conferencias individuales.
  
**Métricas para participantes en la conferencia individuales**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Rol** <br/> |No  <br/> |Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.  <br/> |
|**Participante** <br/> |No  <br/> |Dirección SIP del participante de la conferencia.  <br/> |
|**Conectividad** <br/> |No  <br/> |Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.  <br/> |
|**Modalidad** <br/> |No  <br/> |Tipo de conferencia (por ejemplo, conferencia A/V).  <br/> |
|**Hora de conexión** <br/> |No  <br/> |Fecha y hora en que el participante se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |No  <br/> |Fecha y hora en que el participante abandonó la conferencia.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |
   

