---
title: Informe de comparación de calidad de medios en Skype Empresarial Server
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
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Resumen: obtenga información sobre el informe de comparación de calidad de medios en Skype Empresarial Server.'
ms.openlocfilehash: bb8a14ae9685e53ed2441201b25449bdde3f9b0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817060"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Informe de comparación de calidad de medios en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de comparación de calidad de medios en Skype Empresarial Server.
  
El informe de comparación de calidad de medios sirve para comparar los valores de calidad de diferentes tipos de llamadas de audio (por ejemplo, de las llamadas realizadas en una red inalámbrica frente a las que usan una conexión cableada).
  
## <a name="accessing-the-media-quality-comparison-report"></a>Obtener acceso al informe de comparación de calidad de medios

Al informe de comparación de calidad de medios se obtiene acceso desde la página principal de informes de supervisión. 
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. En la tabla siguiente se muestran los filtros que puede usar en el informe.
  
**Filtros del informe de comparación de calidad de medios**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre empiezan el domingo y finalizan el sábado.  <br/> |
|**Llamadas** <br/> | Tipo de llamada que se va a usar como elemento de comparación principal. Los valores permitidos son: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  No VPN <br/>  Cableado <br/>  Inalámbrica <br/>  Externa y cableada <br/>  Externa e inalámbrica <br/>  Externa y VPN <br/>  Externa y distinta de VPN <br/>  Interna y cableada <br/>  Interna e inalámbrica <br/> |
|**Comparar con llamadas** <br/> | Tipo de llamada que se va a usar como elemento de comparación secundario. Los valores permitidos son: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  No VPN <br/>  Cableado <br/>  Inalámbrica <br/>  Externa y cableada <br/>  Externa e inalámbrica <br/>  Externa y VPN <br/>  Externa y distinta de VPN <br/>  Interna y cableada <br/>  Interna e inalámbrica <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de comparación de calidad de medios.
  
**Métricas del informe de comparación de calidad de medios**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de llamadas** <br/> |No  <br/> |Número total de llamadas.  <br/> |
|**Degradación (MOS)** <br/> |No  <br/> |Cantidad media de degradación de MOS (puntuación de opinión media) experimentada durante una llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0; un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión medias se calculaban haciendo que los usuarios calificara la calidad de una llamada en una escala de 1 a 5. Skype Empresarial Server usa un conjunto de algoritmos para predecir cómo los usuarios hubieran clasificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o un extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |El número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |No  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) alcance el otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden producirse en el enrutamiento de llamadas internacionales, si la configuración del enrutamiento no es la correcta, o si se produce una sobrecarga en el servidor multimedia, y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.  <br/> |
|**Pérdida de paquetes** <br/> |No  <br/> |Tasa media de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. La vibración es una forma de medir la "inestabilidad" de una llamada. Los valores elevados de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |No  <br/> |Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |No  <br/> |Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |No  <br/> |Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones, y esto da lugar a un audio acelerado o distorsionado.  <br/> |
   

