---
title: Informe de resumen de conferencia RTC en Skype Empresarial Server
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
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Resumen: obtenga información sobre el informe de resumen de conferencia RTC en Skype Empresarial Server.'
ms.openlocfilehash: aab91995a2c987e1a6e3a10d1f6fc8791b19a4b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814380"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Informe de resumen de conferencia RTC en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de resumen de conferencia RTC en Skype Empresarial Server.
  
En Skype Empresarial Server, una conferencia RTC es cualquier conferencia en la que al menos un participante llama a la parte de audio mediante un teléfono RTC (red telefónica conmutada). (Un teléfono RTC es un teléfono fijo, un teléfono móvil o cualquier otro teléfono que no use voz sobre IP). Aunque se denominan conferencias RTC en los informes de supervisión, estas conferencias son quizás más conocidas como conferencias de acceso telefónico local.
  
El informe de resumen de conferencias RTC proporciona información acerca de todas las conferencias RTC mantenidas en su organización (es decir, todas las conferencias en las que hubo al menos un usuario de acceso telefónico). El informe incluye información acerca del número total de conferencias RTC, el número total de personas que participaron en dichas conferencias y, quizás lo más importante, el número total de usuarios de acceso telefónico (métrica Total de participantes RTC).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Acceso al informe de resumen de conferencias RTC

El informe de resumen de conferencias RTC solo es accesible desde la página principal de informes de supervisión. Este informe no está vinculado a ningún otro informe. Tenga en cuenta que no se puede recuperar información detallada sobre llamadas para una conferencia RTC, en parte debido a que los responsables de enviar esta información son extremos individuales. Los teléfonos RTC no pueden realizar el seguimiento ni enviar información detallada sobre llamadas.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimización del uso del informe de resumen de conferencias RTC

Para determinar el porcentaje de todas las conferencias que incluyen usuarios de acceso telefónico, compare el valor de la métrica Total de conferencias RTC con la métrica Total de conferencias que se encuentra en el informe de resumen de conferencia de [Skype Empresarial Server.](conference-summary-report.md)
  
Si no ve el número de conferencias RTC que esperaba ver, tenga en cuenta que la capacidad para organizar una conferencia que admita usuarios de acceso telefónico depende de la directiva de conferencias que se haya asignado a un usuario; si muy pocos usuarios pueden organizar conferencias RTC, obviamente verá pocas conferencias RTC. Puede comprobar rápidamente qué directivas de conferencia (si las hay) permiten a los usuarios programar conferencias RTC ejecutando el siguiente comando desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Devolverá unos datos similares a estos:
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de conferencia RTC permite elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.
  
La siguiente tabla contiene los filtros que se pueden usar con el informe de resumen de conferencia RTC.
  
**Filtros del informe de resumen de conferencia RTC**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
   
## <a name="metrics"></a>Métricas

La siguiente tabla contiene la información que recoge el informe de resumen de conferencia RTC.
  
**Métricas del informe de resumen de conferencia RTC**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Diario** <br/> **Semanal** <br/> **Mensualmente** <br/> |No  <br/> |Indica el intervalo temporal seleccionado. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si usa el intervalo Diario y hace clic en 7/7/2015, verá un desglose por horas de la actividad de registro de usuario para esa fecha.  <br/> |
|**Total de conferencias RTC** <br/> |No  <br/> |Número total de conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de participantes** <br/> |No  <br/> |Número total de personas que participaron en conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de minutos de conferencia A/V** <br/> |No  <br/> |Tiempo total de la conferencia audiovisual.  <br/> |
|**Total de minutos de participantes en conferencia A/V** <br/> |No  <br/> |Tiempo total de participación en la conferencia audiovisual. Por ejemplo, si un participante invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes en dicha conferencia será de ocho minutos.  <br/> |
|**Total de participantes RTC** <br/> |No  <br/> |Número total de usuarios que accedió telefónicamente en conferencias donde se permitió el acceso telefónico.  <br/> |
|**Total de minutos de participantes RTC** <br/> |No  <br/> |Tiempo total que los usuarios de acceso telefónico dedicaron a la conferencia. Por ejemplo, si un participante de acceso telefónico invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes RTC será de ocho minutos.  <br/> |
|**Organizadores de conferencia distintos** <br/> |No  <br/> |Número total de usuarios que organizaron al menos una conferencia donde se permitió el acceso telefónico. Los usuarios que hayan organizado más de una conferencia se consideran como un único organizador, igual que los que solo han organizado una conferencia.  <br/> |
   

