---
title: Informe de comparación de calidad Media en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Resumen: Información sobre el informe de comparación de calidad de medios en Skype para Business Server.'
ms.openlocfilehash: bee5e5bc0e619f985d68e18e38aa95377296d2cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926872"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Informe de comparación de calidad Media en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de comparación de calidad de medios en Skype para Business Server.
  
El informe de comparación de calidad de medios sirve para comparar los valores de calidad de diferentes tipos de llamadas de audio (por ejemplo, de las llamadas realizadas en una red inalámbrica frente a las que usan una conexión cableada).
  
## <a name="accessing-the-media-quality-comparison-report"></a>Obtener acceso al informe de comparación de calidad de medios

Al informe de comparación de calidad de medios se obtiene acceso desde la página principal de informes de supervisión. 
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. En la tabla siguiente se muestran los filtros que puede usar en el informe.
  
**Filtros del informe de comparación de calidad de medios**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Llamadas** <br/> | Tipo de llamada que se va a usar como elemento de comparación principal. Los valores permitidos son: <br/>  [Todas] <br/>  Externa <br/>  Interna <br/>  VPN <br/>  Distinto de VPN <br/>  Cableada <br/>  Inalámbrica <br/>  Externa y cableada <br/>  Externa e inalámbrica <br/>  Externa y VPN <br/>  Externa y distinta de VPN <br/>  Interna y cableada <br/>  Interna e inalámbrica <br/> |
|**Comparar con llamadas** <br/> | Tipo de llamada que se va a usar como elemento de comparación secundario. Los valores permitidos son: <br/>  [Todas] <br/>  Externa <br/>  Interna <br/>  VPN <br/>  Distinto de VPN <br/>  Cableada <br/>  Inalámbrica <br/>  Externa y cableada <br/>  Externa e inalámbrica <br/>  Externa y VPN <br/>  Externa y distinta de VPN <br/>  Interna y cableada <br/>  Interna e inalámbrica <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de comparación de calidad de medios.
  
**Métricas del informe de comparación de calidad de medios**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas.  <br/> |
|**Degradación (MOS)** <br/> |No  <br/> |Cantidad promedio de degradación de MOS (puntuación de opinión Media) experimentada durante una llamada. Los valores de degradación pueden oscilar entre una baja de 0,0 y una alta de 5.0; un valor de 0,5 o menos representa degradación aceptable. Tradicionalmente, opinión Media se calculan haciendo que los usuarios valorar la calidad de una llamada en una escala del 1 al 5. Skype para Business Server usa un conjunto de algoritmos para predecir cómo los usuarios habría calificado una llamada.  <br/> Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |No  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**Pérdida de paquetes** <br/> |No  <br/> |Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |No  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |No  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |No  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
   

