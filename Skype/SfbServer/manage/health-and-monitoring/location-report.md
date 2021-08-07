---
title: Informe de ubicación en Skype Empresarial Server
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
ms.assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
description: 'Resumen: obtenga información sobre el informe de ubicación en Skype Empresarial Server.'
ms.openlocfilehash: 0bebc7e04ae97cb90a5a2b2382bfceb679315d5b3442248852b3fb9a4aa31e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276785"
---
# <a name="location-report-in-skype-for-business-server"></a>Informe de ubicación en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de ubicación en Skype Empresarial Server.
  
El informe de ubicaciones proporciona información sobre las métricas de calidad de las llamadas agrupadas por ubicación de red (es decir, por subred de red). Si los usuarios tienen problemas con las llamadas, este informe puede ayudarle a determinar si estos problemas se han extendido o se limitan a un segmento de red determinado.
  
## <a name="accessing-the-location-report"></a>Acceso al informe de ubicaciones

Se obtiene acceso al informe de ubicaciones desde la página principal de informes de supervisión. Para profundizar hasta el informe de lista de llamadas, haga clic en cualquiera de las siguientes métricas:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de ubicaciones le permite filtrar elementos tales como la ubicación del origen de una llamada o si la llamada se realizó desde una conexión inalámbrica o por cable. También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se muestran los filtros que se pueden usar con el informe de ubicaciones
  
**Filtros del informe de ubicaciones**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre empiezan en domingo y terminan en sábado.  <br/> |
|**Ubicación del autor de la llamada** <br/> |Subred de IP del usuario que realizó la llamada. Solo puede seleccionar **[Todos]** para indicar todas las subredes.<br/> |
|**Ubicación del destinatario de la llamada** <br/> |Subred de IP del usuario que recibió la llamada. Solo puede seleccionar **[Todos]** para indicar todas las subredes.<br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  Cableada <br/>  Inalámbrico <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  VPN <br/>  No VPN <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de ubicaciones.
  
**Métricas del informe de ubicaciones**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Subred del autor de la llamada** <br/> |No  <br/> |Subred de IP del usuario que realizó la llamada.  <br/> |
|**Subred del destinatario de la llamada** <br/> |No  <br/> |Subred de IP del usuario que recibió la llamada.  <br/> |
|**Volumen de llamadas** <br/> |Sí  <br/> |Número total de llamadas realizadas.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |Sí  <br/> |Porcentaje de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |Sí  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.  <br/> |
|**Degradación (MOS)** <br/> |Sí  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype Empresarial Server, un conjunto de algoritmos predicen cómo los usuarios habrían clasificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |Sí  <br/> |Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración** <br/> |Sí  <br/> |Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. La vibración es una forma de medir la "inestabilidad" de una llamada. Los valores elevados de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |Sí  <br/> |Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |Sí  <br/> |Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |Sí  <br/> |Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
   

