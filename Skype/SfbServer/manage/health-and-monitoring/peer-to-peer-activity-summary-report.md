---
title: Informe de resumen de actividad punto a punto en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Resumen: Información sobre el informe de resumen de actividad punto a punto en Skype para Business Server.'
ms.openlocfilehash: 0502fc3880a4a04369f6717e67093d359c2b8af7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882575"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Informe de resumen de actividad punto a punto en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de resumen de actividad punto a punto en Skype para Business Server.
  
El Informe de resumen de actividad punto a punto proporciona una vista general de las sesiones de comunicación punto a punto. Una sesión de punto a punto normalmente implica a sólo dos usuarios y no requiere el uso de la Skype para servicios de conferencia de Business Server. En comparación, una conferencia normalmente implica a más de dos usuarios y requiere el uso de Skype para servicios de conferencia de Business Server. La actividad de la conferencia se notifica en el Informe de resumen de conferencia.
  
Con el Informe de resumen de actividad punto a punto le será más fácil responder a preguntas como la siguiente:
  
- ¿Cuántos mensajes instantáneos de punto a punto envían habitualmente mis usuarios en un día normal?
    
- ¿Alguno de Mis usuarios realmente a aprovechar el Skype para las capacidades de transferencia de archivos y uso compartido de aplicaciones Business Server?
    
- Los usuarios se han estado quejando de que en determinados momentos del día, parece que la red va más lenta. ¿Cuántos minutos se dedican a las sesiones de audio o vídeo en esos períodos de tiempo?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Obtener acceso al Informe de resumen de actividad punto a punto

Obtenga acceso al Informe de resumen de actividad punto a punto desde la página inicial de los informes de supervisión. Abra el [informe de mensajería instantánea de punto a punto en Skype para Business Server](im-report.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Total de sesiones de mensajería instantánea de punto a punto
    
- Total de mensajes instantáneos de punto a punto
    
Igualmente, puede abrir el informe de voz y vídeo punto a punto haciendo clic en una de estas métricas:
  
- Total de sesiones de audio de punto a punto
    
- Total de minutos de sesiones de audio punto a punto
    
- Total de sesiones de audio punto a punto
    
- Total de minutos de sesiones de audio punto a punto
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Sacar el máximo provecho del Informe de resumen de actividad punto a punto

En la parte inferior del Informe de resumen de actividad punto a punto encontrará los totales de métricas como Sesiones de mensajería instantánea punto a punto o Total de mensajes de mensajería instantánea punto a punto. De esta forma obtiene un resumen rápido de la información detallada encontrada en el cuerpo del informe.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el resumen de actividad punto a punto le permite elegir cuántos datos agrupar. En este caso, la actividad se agrupa por hora, día, semana o mes.
  
En la siguiente tabla se enumeran los filtros que puede utilizar con el Informe de resumen de actividad punto a punto.
  
**Filtros del Informe de resumen de actividad punto a punto**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 17/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de resumen de actividad punto a punto.
  
**Métricas del Informe de resumen de actividad punto a punto**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Cada día** <br/> **Cada semana** <br/> **Cada mes** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 17/07/2015, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.  <br/> |
|**Total de sesiones punto a punto** <br/> |No  <br/> |Cantidad total de sesiones punto a punto realizadas, independientemente del tipo de sesión.  <br/> |
|**Total de sesiones de mensajería instantánea de punto a punto** <br/> |No  <br/> |Cantidad total de sesiones de mensajería instantánea punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de mensajes instantáneos de punto a punto** <br/> |No  <br/> |Cantidad total de mensajes instantáneos enviados en sesiones punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de sesiones de audio punto a punto** <br/> |No  <br/> |Cantidad total de llamadas de audio punto a punto. Cuando se hace clic en este campo, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de minutos de sesiones de audio punto a punto** <br/> |No  <br/> |Cantidad de tiempo total transcurrida en sesiones de audio punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Promedio de minutos en sesiones de audio punto a punto** <br/> |No  <br/> |Cantidad de tiempo promedio transcurrido en sesiones de audio punto a punto. Se calcula dividiendo el total del tiempo de sesiones de audio por el número total de sesiones de audio.  <br/> |
|**Total de sesiones de vídeo punto a punto** <br/> |No  <br/> |Cantidad total de llamadas de vídeo punto a punto. Observe que las sesiones de vídeo también se cuentan como sesiones de audio: cada sesión de vídeo se cuenta como una sesión de vídeo y una sesión de audio. Cuando se hace clic en este elemento, el informe muestra el informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de minutos de sesiones de vídeo punto a punto** <br/> |No  <br/> |Cantidad total de tiempo transcurrido en sesiones de vídeo punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Promedio de minutos en sesiones de vídeo punto a punto** <br/> |No  <br/> |Cantidad de tiempo promedio transcurrido en sesiones de vídeo punto a punto. Se calcula dividiendo el total del tiempo de sesiones de vídeo por el número total de sesiones de vídeo.  <br/> |
|**Total de sesiones de transferencia de archivos punto a punto** <br/> |No  <br/> |Cantidad total de sesiones punto a punto en las que se realizaron transferencias de archivos.  <br/> |
|**Total de sesiones compartidas de aplicaciones punto a punto** <br/> |No  <br/> |Cantidad total de sesiones punto a punto en las que se compartieron aplicaciones  <br/> |
   

