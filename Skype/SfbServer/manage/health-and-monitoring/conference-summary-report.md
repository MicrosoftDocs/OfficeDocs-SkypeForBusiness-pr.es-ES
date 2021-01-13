---
title: Informe de resumen de conferencia en Skype Empresarial Server
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
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Resumen: obtenga información sobre el informe de resumen de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: eaaa97c54a9183beda40848795b454e7dec92c6f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817050"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Informe de resumen de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de resumen de conferencia en Skype Empresarial Server.
  
El informe de resumen de conferencia ofrece una vista general de las sesiones de conferencia en línea. Una conferencia suele implicar a más de 2 usuarios y requiere el uso de servicios de conferencia. En comparación, una sesión punto a punto normalmente implica solo 2 usuarios y no requiere el uso de los servicios de conferencia de Skype Empresarial Server. Las actividades punto a punto se notifican en el informe de resumen de actividad punto a punto [en Skype Empresarial Server.](peer-to-peer-activity-summary-report.md)
  
El Informe de resumen de conferencia no solo indica cuántas conferencias se han realizado durante un período de tiempo determinado (cada hora, día, semana, mes), sino que también indica el número total de personas que participaron en dichas conferencias y el número total de organizadores de conferencias únicos.
  
Un organizador "único" es cualquier persona que programe al menos una conferencia. Por ejemplo, si Pilar Ackerman programa una conferencia, cuenta como un organizador único. Si Ken Myer programa 148 conferencias, también cuenta como un organizador único. Por ejemplo, en la tabla siguiente se muestran 8 conferencias programadas, pero solo tres organizadores únicos (Ken Myer, Pilar Ackerman y David Ahs).
  
|**Organizador de la conferencia**|**Fecha de la conferencia**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00 AM  <br/> |
|David Ahs  <br/> |7/7/2015 10:00 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
El informe de resumen de conferencia también indica el número de conferencias que incluyeron audio y/o vídeo.
  
## <a name="accessing-the-conference-summary-report"></a>Acceso al informe de resumen de conferencia

Puede acceder al informe de resumen de conferencia desde la página principal de informes de supervisión. Para llegar hasta dicho informe, deberá hacer clic en las siguientes métricas:
  
- Total de conferencias
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usar el informe de resumen de conferencia de la mejor forma posible

Los valores totales de la mayoría de las métricas usadas en el informe de resumen de conferencia se pueden encontrar en la parte inferior del informe; desplácese hacia abajo para ver valores como el número total de conferencias realizadas durante el período de tiempo especificado y el número total de personas que participaron en dichas conferencias. Una métrica que no se suma en la parte inferior del informe son los organizadores de conferencias únicos totales. ¿Por qué no? Este es un motivo. Supongamos que está viendo los datos de un mes. El día 1 tenía 34 organizadores de conferencia únicos; el día 2 tenía 27 organizadores de conferencia únicos. ¿Significa que tenía 61 organizadores de conferencia únicos durante esos dos días? No necesariamente. Después de todo, las 27 personas que organizaron conferencias el día 2 podrían estar entre las 34 personas que organizaron conferencias el día 1. Por ejemplo, en este informe sencillo, tenga en cuenta que Ken Myer y Pilar Ackerman programaron conferencias el 7/7/7/2015 y el 2/7/2015:
  
|**Organizador de la conferencia**|**Fecha de la conferencia**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00 AM  <br/> |
|David Ahs  <br/> |7/7/2015 10:00 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
Para componerse una mejor idea del número total de usuarios distintos que ha organizado conferencias, cambie el intervalo temporal (por ejemplo, consulte los datos por mes en lugar de por día).
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de conferencia le permite elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.
  
La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.
  
**Filtros del informe de resumen de conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (empezando por la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
   
## <a name="metrics"></a>Métricas

La siguiente tabla incluye la información que ofrece el informe de resumen de conferencia.
  
**Métricas del informe de resumen de conferencia**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Diario** <br/> **Semanal** <br/> **Mensualmente** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si usa el intervalo Diario y hace clic en 7/7/2015, verá un desglose por horas de la actividad de registro de usuario para esa fecha.  <br/> |
|**Total de conferencias** <br/> |No  <br/> |Número total de conferencias (independientemente del tipo de conferencia) celebradas. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.  <br/> |
|**Total de participantes** <br/> |No  <br/> |Número total de personas que participaron en las conferencias. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.  <br/> |
|**Media de participantes por conferencia** <br/> |No  <br/> |Número medio de participantes que participaron en una conferencia en concreto. Se calcula dividiendo el número total de conferencias por el número total de participantes.  <br/> |
|**Número total de conferencias A/V** <br/> |No  <br/> |Número total de conferencias que incluían audio o vídeo.  <br/> |
|**Total de minutos de conferencia A/V** <br/> |No  <br/> |Número total de minutos dedicados a conferencias de audio/vídeo.  <br/> La métrica Total de minutos de conferencia A/V resume todos los tipos de conferencias audiovisuales, incluidos: conferencias A/V; Conferencias de mensajería instantánea; conferencias de uso compartido de aplicaciones; conferencias de datos; y conferencias RTC.  <br/> |
|**Total de minutos de participantes en conferencia A/V** <br/> |No  <br/> |Número total de minutos de los participantes dedicados a conferencias de audio/vídeo. Por ejemplo, supongamos que un usuario participa 5 minutos en una conferencia de audio/vídeo y un segundo usuario participa 3 minutos en la misma conferencia. Esto hace un total de 8 minutos de los participantes: 5 minutos más 3 minutos.  <br/> |
|**Número medio de minutos en conferencias A/V** <br/> |No  <br/> |Número medio de minutos por conferencia de audio/vídeo.  <br/> |
|**Número total de organizadores únicos de conferencias** <br/> |No  <br/> |Número total de usuarios que organizaron al menos una conferencia. Los usuarios que organizaron más de una conferencia se cuentan como un único organizador, al igual que ocurre con los usuarios que solo organizaron una única conferencia.  <br/> |
|**Número total de mensajes de conferencias** <br/> |No  <br/> |Número total de mensajes instantáneos enviados durante las conferencias.  <br/> |
   

