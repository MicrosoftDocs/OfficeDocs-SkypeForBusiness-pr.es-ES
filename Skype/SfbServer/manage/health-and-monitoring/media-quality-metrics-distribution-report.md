---
title: Informe de distribución de métricas de calidad de medios en Skype Empresarial Server
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
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Resumen: obtenga información sobre el informe de distribución de métricas de calidad de medios en Skype Empresarial Server.'
ms.openlocfilehash: c39282ab2d5d6ce903affd807d22116a98de3620
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827810"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Informe de distribución de métricas de calidad de medios en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre el informe de distribución de métricas de calidad de medios en Skype Empresarial Server.
  
El Informe de distribución de métricas de calidad de medios permite ver un gráfico que muestra los valores de distribución de una métrica de calidad de experiencia como la vibración o la pérdida de paquetes. Por ejemplo, supongamos que los usuarios realizan un total de 10 llamadas telefónicas. Estas 10 llamadas telefónicas tienen los siguientes tiempos de ida y vuelta:
  
|**Número de llamada**|**Tiempo de ida y vuelta (milisegundos)**|
|:-----|:-----|
|1   <br/> |50  <br/> |
|2   <br/> |50  <br/> |
|3   <br/> |50  <br/> |
|4   <br/> |50  <br/> |
|5   <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10    <br/> |50  <br/> |
   
El promedio de esos tiempos de ida y vuelta es de 500 milisegundos (5000 divididos por 10). 500 milisegundos es un tiempo de ida y vuelta extremadamente grande; como resultado, puede pensar que tiene un problema grave con la congestión de la red. (Los tiempos de ida y vuelta largos suelen ser el resultado de redes sobrecargadas).
  
En realidad, por supuesto, el 90 % de las llamadas tenían tiempos de ida y vuelta excelentes; simplemente ha tenido una llamada mala que ha distorsionado los resultados generales. Si solo observa el tiempo promedio de ida y vuelta, podría llegar a una conclusión muy incorrecta.
  
Con el informe de distribución de métricas de calidad de medios le será más fácil evitar llegar a conclusiones erróneas, ya que muestra una distribución gráfica de una métrica especificada (como el tiempo de ida y vuelta). Con estos gráficos le resultará más fácil ver que tiene nueve llamadas buenas y una llamada muy mala. Probablemente querrá seguir investigando esa única llamada, pero el hecho de que 9 de las 10 llamadas fueran muy buenas sugiere que no hay ningún motivo para efectuar ningún cambio drástico en la red, al menos no en este momento.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de distribución de métricas de calidad de medios.
  
**Filtros del informe de distribución de métricas de calidad de medios**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Mínimo en eje x** <br/> |Valor mínimo que se visualizará en el eje X del gráfico.  <br/> |
|**Máximo en eje x** <br/> |Valor máximo que se visualizará en el eje X del gráfico.  <br/> |
|**Tipo de acceso** <br/> | Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todos] <br/>  VPN <br/>  No VPN <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todos] <br/>  Cableado <br/>  Inalámbrica <br/> |
   

