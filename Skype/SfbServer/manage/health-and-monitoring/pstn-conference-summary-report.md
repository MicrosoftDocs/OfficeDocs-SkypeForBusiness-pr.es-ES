---
title: Informe de resumen de conferencia RTC en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Resumen: Conozca el informe resumen de conferencia PSTN en Skype para Business Server 2015.'
ms.openlocfilehash: 1897b6ebf25e4de4f60af91d76ada539ea3561f9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server-2015"></a>Informe de resumen de conferencia RTC en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre el informe resumen de conferencia PSTN en Skype para Business Server 2015.
  
En Skype para Business Server 2015, una conferencia de RTC es una conferencia en la que como mínimo un participante se conecta a la parte de audio mediante el uso de un teléfono PSTN (red telefónica pública conmutada). (Un teléfono PSTN es un "fijo", un teléfono celular o cualquier otro número de teléfono que no haga uso de la voz sobre IP.) Aunque se conoce como conferencias PSTN en los informes de supervisión, estas conferencias quizás se conoce más comúnmente como conferencias de acceso telefónico.
  
El informe de resumen de conferencias RTC proporciona información sobre todas las conferencias RTC mantenidas en su organización (es decir, todas las conferencias en las que hubo al menos un usuario de acceso telefónico). El informe incluye información sobre la cantidad total de conferencias RTC, la cantidad total de personas que participaron en dichas conferencias y, quizás lo más importante, la cantidad total de usuarios de acceso telefónico (métrica Total de participantes RTC).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Acceso al informe de resumen de conferencias RTC

El informe de resumen de conferencias RTC solo es accesible desde la página principal de informes de supervisión. Este informe no está vinculado a ningún otro informe. Tenga en cuenta que no se puede recuperar información detallada sobre llamadas para una conferencia RTC, en parte porque los responsables de enviar esta información son extremos individuales. Los teléfonos RTC no pueden realizar el seguimiento ni enviar información detallada sobre llamadas.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimización del uso del informe de resumen de conferencias RTC

Para determinar el porcentaje de todas las conferencias que incluyen usuarios de acceso telefónico, comparar el valor de la métrica de conferencias PSTN Total con la métrica Total de conferencias se encuentra en el [Informe de resumen de conferencia en Skype para Business Server 2015](conference-summary-report.md).
  
Si no ve la cantidad de conferencias RTC que esperaba ver, tenga en cuenta que la capacidad para organizar una conferencia que admita usuarios de acceso telefónico depende de la directiva de conferencias que se haya asignado a un usuario; si muy pocos usuarios pueden organizar conferencias RTC, obviamente verá pocas conferencias RTC. Para comprobar rápidamente que las directivas de conferencia (si existe) de permitir a los usuarios programar conferencias PSTN ejecutando el siguiente comando desde dentro el Skype para el Shell de administración de servidor de Business:
  
```
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Se devolverán datos similares a estos:
  
```
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True

```

## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de conferencia RTC permite elegir el modo en que los datos deben agruparse (en este caso, las conferencias se agrupan por hora, día, semana o mes).
  
La siguiente tabla contiene los filtros que se pueden usar con el informe de resumen de conferencia RTC.
  
**Filtros de informe de resumen de conferencias PSTN**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
   
## <a name="metrics"></a>Métricas

La siguiente tabla contiene la información que recoge el informe de resumen de conferencia RTC.
  
**Métricas de informe de resumen de conferencias PSTN**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Cada día** <br/> **Cada semana** <br/> **Cada mes** <br/> |No  <br/> |Indica el intervalo temporal seleccionado. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 07/07/2015, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.  <br/> |
|**Total de conferencias RTC** <br/> |No  <br/> |Cantidad total de conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de participantes** <br/> |No  <br/> |Cantidad total de personas que participaron en conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de minutos de conferencia A/V** <br/> |No  <br/> |Tiempo total de la conferencia audiovisual.  <br/> |
|**Total de minutos de participantes en conferencia A/V** <br/> |No  <br/> |Tiempo total de participación en la conferencia audiovisual. Por ejemplo, si un participante invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes en dicha conferencia será de ocho minutos.  <br/> |
|**Total de participantes RTC** <br/> |No  <br/> |Cantidad total de usuarios que obtuvo acceso telefónicamente en conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de minutos de participantes RTC** <br/> |No  <br/> |Tiempo total que los usuarios de acceso telefónico dedicaron a la conferencia. Por ejemplo, si un participante de acceso telefónico invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes RTC será de ocho minutos.  <br/> |
|**Organizadores de conferencia únicos** <br/> |No  <br/> |Cantidad total de usuarios que organizaron al menos una conferencia donde se permitió el acceso telefónico. Los usuarios que hayan organizado más de una conferencia se consideran como un único organizador, igual que los que solo han organizado una conferencia.  <br/> |
   

