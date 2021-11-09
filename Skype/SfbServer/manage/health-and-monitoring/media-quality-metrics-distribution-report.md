---
title: Informe de distribución de métricas de calidad multimedia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Summary: Learn about the Media Quality Metrics Distribution Report in Skype Empresarial Server.'
ms.openlocfilehash: 00899681190e532af971c719c2e81f655facf7ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862317"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Informe de distribución de métricas de calidad multimedia en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre el Informe de distribución de métricas de calidad multimedia en Skype Empresarial Server.
  
El Informe de distribución de métricas de calidad de medios permite ver un gráfico que muestra los valores de distribución de una métrica de calidad de experiencia como la vibración o la pérdida de paquetes. Por ejemplo, supongamos que los usuarios realizan un total de 10 llamadas telefónicas. Estas 10 llamadas telefónicas tienen los siguientes tiempos de ida y vuelta:
  
|**Número de llamada**|**Tiempo de ida y vuelta (milisegundos)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
El promedio de esos tiempos de ida y vuelta es de 500 milisegundos (5000 divididos por 10). Quinientos milisegundos es un tiempo de ida y vuelta extremadamente grande; como resultado, es posible que crea que tiene un problema grave con la congestión de la red. (Los tiempos de ida y vuelta largos suelen ser el resultado de redes sobrecargadas).
  
En realidad, por supuesto, el 90 % de las llamadas tenían excelentes tiempos de ida y vuelta; simplemente tenías una llamada mala que sesgaba los resultados generales. Si solo observa el tiempo promedio de ida y vuelta, puede llegar a una conclusión muy incorrecta.
  
Con el informe de distribución de métricas de calidad de medios le será más fácil evitar llegar a conclusiones erróneas, ya que muestra una distribución gráfica de una métrica especificada (como el tiempo de ida y vuelta). Con estos gráficos le resultará más fácil ver que tiene nueve llamadas buenas y una llamada muy mala. Probablemente querrá seguir investigando esa única llamada, pero el hecho de que 9 de las 10 llamadas fueran muy buenas sugiere que no hay ningún motivo para efectuar ningún cambio drástico en la red, al menos no en este momento.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de distribución de métricas de calidad de medios.
  
**Filtros del informe de distribución de métricas de calidad de medios**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Mínimo en eje x** <br/> |Valor mínimo que se visualizará en el eje X del gráfico.  <br/> |
|**Máximo en eje x** <br/> |Valor máximo que se visualizará en el eje X del gráfico.  <br/> |
|**Tipo de acceso** <br/> | Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  Interno <br/>  Externo <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  VPN <br/>  No VPN <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  Cableada <br/>  Inalámbrico <br/> |
   

