---
title: El informe calidad de medios métricas distribución en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Resumen: Información sobre el informe calidad de medios métricas distribución en Skype para Business Server.'
ms.openlocfilehash: ef15807cdc0377d2548a83f8da56de9b6cf85e04
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014141"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>El informe calidad de medios métricas distribución en Skype para Business Server 
 
**Resumen:** Obtenga información sobre el informe calidad de medios métricas distribución en Skype para Business Server.
  
El Informe de distribución de métricas de calidad de medios permite ver un gráfico que muestra los valores de distribución de una métrica de calidad de experiencia como la vibración o la pérdida de paquetes. Por ejemplo, supongamos que los usuarios realizan un total de 10 llamadas telefónicas. Estas 10 llamadas telefónicas tienen los siguientes tiempos de ida y vuelta:
  
|**Número de llamada**|**Tiempo de recorrido de ida y vuelta (milisegundos)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6  <br/> |50  <br/> |
|7  <br/> |50  <br/> |
|8  <br/> |4550  <br/> |
|9  <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
El promedio de estos tiempos de ida y vuelta es de 500 milisegundos (5000 dividido por 10). Quinientos milisegundos es un tiempo de ida y vuelta extremadamente elevado; por ello, se podría llegar a creer que tiene un problema grave de congestión de la red (normalmente, los tiempos de ida y vuelta elevados se producen por una sobrecarga de la red).
  
En realidad, el 90 % de las llamadas tiene unos tiempos de ida y vuelta excelentes. Solo tiene una llamada mala que modificó los resultados generales. Si mira únicamente el tiempo promedio de ida y vuelta, podría llegar a una conclusión errónea.
  
Con el informe de distribución de métricas de calidad de medios le será más fácil evitar llegar a conclusiones erróneas, ya que muestra una distribución gráfica de una métrica especificada (como el tiempo de ida y vuelta). Con estos gráficos le resultará más fácil ver que tiene nueve llamadas buenas y una llamada muy mala. Probablemente querrá seguir investigando esa única llamada, pero el hecho de que 9 de las 10 llamadas fueran muy buenas sugiere que no hay ningún motivo para efectuar ningún cambio drástico en la red, al menos no en este momento.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de distribución de métricas de calidad de medios.
  
**Filtros del informe de distribución de métricas de calidad de medios**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Mínimo en eje x** <br/> |Valor mínimo que se visualizará en el eje X del gráfico.  <br/> |
|**Máximo en eje x** <br/> |Valor máximo que se visualizará en el eje X del gráfico.  <br/> |
|**Tipo de acceso** <br/> | Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Interno <br/>  Externo <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  VPN <br/>  Distinto de VPN <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Cableada <br/>  Inalámbrica <br/> |
   

