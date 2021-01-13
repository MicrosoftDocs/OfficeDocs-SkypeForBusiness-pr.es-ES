---
title: Informe de resumen de actividad punto a punto en Skype Empresarial Server
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
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Resumen: obtenga información sobre el informe de resumen de actividad punto a punto en Skype Empresarial Server.'
ms.openlocfilehash: b1dddaefc7e824bc7b4387d13c92143e253d69f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816800"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Informe de resumen de actividad punto a punto en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de resumen de actividad punto a punto en Skype Empresarial Server.
  
El Informe de resumen de actividad punto a punto proporciona una vista general de las sesiones de comunicación punto a punto. Una sesión punto a punto normalmente implica solo dos usuarios y no requiere el uso de los servicios de conferencia de Skype Empresarial Server. En comparación, una conferencia suele implicar a más de dos usuarios y requiere el uso de los servicios de conferencia de Skype Empresarial Server. La actividad de la conferencia se notifica en el Informe de resumen de conferencia.
  
Con el Informe de resumen de actividad punto a punto le será más fácil responder a preguntas como la siguiente:
  
- ¿Cuántos mensajes instantáneos de punto a punto envían habitualmente mis usuarios en un día normal?
    
- ¿Alguno de mis usuarios aprovecha realmente las capacidades de uso compartido de aplicaciones y transferencia de archivos de Skype Empresarial Server?
    
- Los usuarios se han estado quejando de que en determinados momentos del día, parece que la red va más lenta. ¿Cuántos minutos se dedican a las sesiones de audio o vídeo en esos períodos de tiempo?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acceder al Informe de resumen de actividad punto a punto

Acceda al Informe de resumen de actividad punto a punto desde la página inicial de los informes de supervisión. Para abrir el informe de mensajería instantánea punto a punto [en Skype Empresarial Server,](im-report.md) haga clic en cualquiera de las métricas siguientes:
  
- Total de sesiones de MI punto a punto
    
- Total de mensajes instantáneos punto a punto
    
Igualmente, puede abrir el informe de voz y vídeo punto a punto haciendo clic en una de estas métricas:
  
- Total de sesiones de audio punto a punto
    
- Total de minutos de sesiones de audio punto a punto
    
- Total de sesiones de audio punto a punto
    
- Total de minutos de sesiones de audio punto a punto
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Sacar el máximo provecho del Informe de resumen de actividad punto a punto

En la parte inferior del Informe de resumen de actividad punto a punto encontrará los totales de métricas como Sesiones de mensajería instantánea punto a punto o Total de mensajes de mensajería instantánea punto a punto. De esta forma obtiene un resumen rápido de la información detallada encontrada en el cuerpo del informe.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el resumen de actividad punto a punto le permite elegir cuántos datos agrupar. En este caso, la actividad se agrupa por hora, día, semana o mes.
  
En la siguiente tabla se enumeran los filtros que puede utilizar con el Informe de resumen de actividad punto a punto.
  
**Filtros del Informe de resumen de actividad punto a punto**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 17/7/12015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/17/12015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/13/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 17/7/12015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/17/12015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/13/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 17/7/12015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/12015 de 12:00 a 9/7/12015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de resumen de actividad punto a punto.
  
**Métricas del Informe de resumen de actividad punto a punto**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Diario** <br/> **Semanal** <br/> **Mensualmente** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si usa el intervalo Diario y hace clic en 17/7/12015, verá un desglose por horas de la actividad de registro de usuario para esa fecha.  <br/> |
|**Total de sesiones punto a punto** <br/> |No  <br/> |Número total de sesiones punto a punto realizadas, independientemente del tipo de sesión.  <br/> |
|**Total de sesiones de MI punto a punto** <br/> |No  <br/> |Número total de sesiones de mensajería instantánea punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de mensajes instantáneos punto a punto** <br/> |No  <br/> |Número total de mensajes instantáneos enviados en sesiones punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de sesiones de audio punto a punto** <br/> |No  <br/> |Número total de llamadas de audio punto a punto. Cuando se hace clic en este campo, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de minutos de sesiones de audio punto a punto** <br/> |No  <br/> |Cantidad de tiempo total transcurrida en sesiones de audio punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Promedio de minutos en sesiones de audio punto a punto** <br/> |No  <br/> |Cantidad de tiempo promedio transcurrido en sesiones de audio punto a punto. Se calcula dividiendo el total del tiempo de sesiones de audio por el número total de sesiones de audio.  <br/> |
|**Total de sesiones de vídeo punto a punto** <br/> |No  <br/> |Número total de llamadas de vídeo punto a punto. Observe que las sesiones de vídeo también se cuentan como sesiones de audio: cada sesión de vídeo se cuenta como una sesión de vídeo y una sesión de audio. Cuando se hace clic en este elemento, el informe muestra el informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Total de minutos de sesiones de vídeo punto a punto** <br/> |No  <br/> |Cantidad total de tiempo transcurrido en sesiones de vídeo punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.  <br/> |
|**Promedio de minutos en sesiones de vídeo punto a punto** <br/> |No  <br/> |Cantidad de tiempo promedio transcurrido en sesiones de vídeo punto a punto. Se calcula dividiendo el total del tiempo de sesiones de vídeo por el número total de sesiones de vídeo.  <br/> |
|**Total de sesiones de transferencia de archivos punto a punto** <br/> |No  <br/> |Número total de sesiones punto a punto en las que se realizaron transferencias de archivos.  <br/> |
|**Total de sesiones compartidas de aplicaciones punto a punto** <br/> |No  <br/> |Número total de sesiones punto a punto en las que se compartieron aplicaciones  <br/> |
   

