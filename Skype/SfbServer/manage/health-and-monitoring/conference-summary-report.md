---
title: Informe de resumen de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Resumen: Información sobre el informe de resumen de conferencia en Skype para Business Server.'
ms.openlocfilehash: a6b494395a1d4074907947ef626f9d36b4e239db
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197670"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Informe de resumen de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de resumen de conferencia en Skype para Business Server.
  
El informe de resumen de conferencia ofrece una vista general de las sesiones de conferencia en línea. Normalmente, una conferencia implica a más de 2 los usuarios y requiere el uso de servicios de conferencia. En comparación, una sesión de punto a punto normalmente implica a sólo 2 los usuarios y no requiere el uso de Skype para servicios de conferencia de Business Server. En el [informe de resumen de actividad punto a punto en Skype para Business Server](peer-to-peer-activity-summary-report.md)se informan de las actividades de punto a punto.
  
El informe de resumen de conferencia no sólo indica cuántas de las conferencias llevadas durante un período de tiempo determinado (cada hora, diariamente, semanalmente, mensualmente) pero también se indica el número total de personas que participaron en dichas conferencias y el número total de conferencia único organizadores.
  
Un organizador "único" es cualquier persona que programa al menos una conferencia. Por ejemplo, si Pilar Ackerman programa una conferencia cuenta como un organizador único. Si el programa de Ken Myer 148 conferencias él, los recuentos demasiado como un organizador único. Por ejemplo, en la siguiente tabla muestra 8 conferencias programadas, pero sólo tres organizadores únicos (Ken Myer, Pilar Ackerman y David Ahs).
  
|**Organizador de la conferencia**|**Fecha de la conferencia**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 10:00  <br/> |
|David Ahs  <br/> |07/07/2015 10:00  <br/> |
|Ken Myer  <br/> |07/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 11:00  <br/> |
|Ken Myer  <br/> |07/07/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
El informe de resumen de conferencia también indica la cantidad de conferencias que incluyeron audio o vídeo.
  
## <a name="accessing-the-conference-summary-report"></a>Acceso al informe de resumen de conferencia

Puede obtener acceso al informe de resumen de conferencia desde la página principal de informes de supervisión. Para llegar hasta dicho informe, necesitará hacer clic en las siguientes métricas:
  
- Total de conferencias
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usar el informe de resumen de conferencia de la mejor forma posible

Totales valores para la mayoría de las métricas que se usa en el informe de resumen de conferencia se pueden encontrar en la parte inferior del informe; Desplácese hacia abajo hasta vea valores, como el número total de las conferencias llevadas durante el período de tiempo especificado y el número total de personas que participaron en dichas conferencias. Una métrica que no se suman en la parte inferior del informe es los organizadores de conferencias único Total. ¿Por qué no? Hay una razón. Suponga que desea en el valor de un mes de datos. En el día 1 tenía organizadores de conferencia 34 distintos; en el día 2 tenía 27 organizadores de conferencia distintos. ¿Significa que tenía 61 organizadores de conferencia distintos para esos dos días? No necesariamente. Después de todo, todas las 27 personas que organizó conferencias en día 2 posible entre las 34 personas que organizó conferencias en día 1. Por ejemplo, en este informe simple, tenga en cuenta que el Ken Myer y Pilar Ackerman de programar conferencias ambos en 7/7/2015 y en 2/7/2015:
  
|**Organizador de la conferencia**|**Fecha de la conferencia**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 10:00  <br/> |
|David Ahs  <br/> |07/07/2015 10:00  <br/> |
|Ken Myer  <br/> |07/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 11:00  <br/> |
|Ken Myer  <br/> |07/07/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
Para componerse una mejor idea de la cantidad total de usuarios distintos que ha organizado conferencias, cambie el intervalo temporal (por ejemplo, consulte los datos por mes en lugar de por día).
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de conferencia le permite elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.
  
La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.
  
**Filtros del informe de resumen de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
   
## <a name="metrics"></a>Métricas

La siguiente tabla incluye la información que ofrece el informe de resumen de conferencia.
  
**Métricas del informe de resumen de conferencia**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Cada día** <br/> **Cada semana** <br/> **Cada mes** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 07/07/2015, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.  <br/> |
|**Total de conferencias** <br/> |No  <br/> |Cantidad total de conferencias (independientemente del tipo de conferencia) celebradas. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.  <br/> |
|**Total de participantes** <br/> |No  <br/> |Cantidad total de personas que participaron en las conferencias. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.  <br/> |
|**Media de participantes por conferencia** <br/> |No  <br/> |Cantidad media de participantes que participaron en una conferencia en concreto. Se calcula dividiendo la cantidad total de conferencias por la cantidad total de participantes.  <br/> |
|**Cantidad total de conferencias A/V** <br/> |No  <br/> |Cantidad total de conferencias que incluían audio o vídeo.  <br/> |
|**Total de minutos de conferencia A/V** <br/> |No  <br/> |Cantidad total de minutos dedicados a conferencias de audio/vídeo.  <br/> El Total A / métrica de minutos de conferencia V resume todos los tipos de conferencia de audio/vídeo, incluidos: A / conferencias V; Conferencias de mensajería instantánea; aplicación de uso compartido de las conferencias; conferencias de datos; y las conferencias de RTC.  <br/> |
|**Total de minutos de participantes en conferencia A/V** <br/> |No  <br/> |Cantidad total de minutos de los participantes dedicados a conferencias de audio/vídeo. Por ejemplo, supongamos que un usuario participa 5 minutos en una conferencia de audio/vídeo y un segundo usuario participa 3 minutos en la misma conferencia. Esto hace un total de 8 minutos de los participantes: 5 minutos más 3 minutos.  <br/> |
|**Cantidad media de minutos en conferencias A/V** <br/> |No  <br/> |Cantidad media de minutos por conferencia de audio/vídeo.  <br/> |
|**Cantidad total de organizadores únicos de conferencias** <br/> |No  <br/> |Cantidad total de usuarios que organizaron al menos una conferencia. Los usuarios que organizaron más de una conferencia se cuentan como un único organizador, al igual que ocurre con los usuarios que solo organizaron una única conferencia.  <br/> |
|**Cantidad total de mensajes de conferencias** <br/> |No  <br/> |Cantidad total de mensajes instantáneos enviados durante las conferencias.  <br/> |
   

