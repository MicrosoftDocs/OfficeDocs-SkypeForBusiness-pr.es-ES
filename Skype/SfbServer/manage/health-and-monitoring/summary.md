---
title: Informe del resumen de calidad de medios en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/29/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Resumen: Conozca el informe resumen de calidad de los medios de comunicación en Skype para Business Server 2015.'
ms.openlocfilehash: 3691995cfc826bc4fb214800a36a6d51177a9cd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="media-quality-summary-report-in-skype-for-business-server-2015"></a>Informe del resumen de calidad de medios en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre el informe resumen de calidad de los medios de comunicación en Skype para Business Server 2015.
  
El Informe de resumen de calidad de medios es, quizás, la mejor opción para analizar la calidad de las llamadas en su organización: este informe proporciona métricas de llamadas de calidad de la experiencia (QoE) detalladas y desglosadas en las siguientes categorías:
  
- Llamadas de punto a punto UC (como un Skype para negocio tenga Skype para llamada de negocio)
    
- Sesiones de conferencia de UC
    
- Sesiones de conferencia de RTC
    
- Llamadas RTC: desvío de medios
    
- Llamadas RTC (sin desvío): sección de UC
    
- Llamadas RTC (sin desvío): sección de puerta de enlace
    
- Otros tipos de llamada
    
Al abrir el informe por primera vez, se ve la información de resumen de cada una de estas categorías. Sin abandonar el informe, puede expandir cada categoría mirar subcategorías como llamadas realizadas desde Office Communicator 2007 R2 a Skype para el negocio. A su vez, puede profundizar en esas subcategorías para ver detalles sobre cada llamada realizada dentro de esa subcategoría.
  
En Skype para Business Server 2015 aún más el informe de resumen de calidad del medio divide los datos en tres tipos de llamada: llamadas audio, vídeo y llamadas de compartir aplicaciones. Cada tipo de llamada tiene su propia sección en el informe y su propio conjunto personalizado de métricas de llamada.
  
El Informe de resumen de calidad de medios también permite aplicar filtros para poder comparar la calidad de las llamadas: llamadas por cable frente a inalámbricas, llamadas internas frente a externas y llamadas de VPN frente a llamadas distintas de VPN.
  
## <a name="accessing-the-media-quality-summary-report"></a>Acceso al Informe de resumen de calidad de medios

Al Informe de resumen de calidad de medios se obtiene acceso desde la página principal de Informes de supervisión. Puede desglosar el [Informe de lista de llamar en Skype para Business Server 2015](call-list-report-0.md) haciendo clic en cualquiera de las siguientes métricas:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
Además, puede obtener acceso al Informe de resumen de calidad de medios haciendo clic en cualquiera de las siguientes métricas de llamadas de audio:
  
- Recorrido de ida y vuelta (ms)
    
- Degradación (MOS)
    
- Pérdida de paquetes
    
- Vibración (ms)
    
- Tasa de recuperación de muestras ocultas
    
- Tasa de recuperación de muestras extendidas
    
- Tasa de recuperación de muestras comprimidas
    
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de calidad de los medios permite filtrar los datos devueltos por el tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de resumen de calidad de los medios.
  
**Filtros de informe de resumen de calidad Media**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Tipo de acceso** <br/> | Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Cableada <br/>  Inalámbrica <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  VPN <br/>  Distinto de VPN <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de resumen de calidad de los medios.
  
**Métricas de informe de resumen de calidad Media: Resumen de llamada de Audio**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada/tipo de extremo** <br/> |No  <br/> | Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son: <br/>  Llamadas de punto a punto de UC <br/>  Sesiones de conferencia de UC <br/>  Sesiones de conferencia de RTC <br/>  Llamadas RTC: desvío de medios <br/>  Llamadas RTC (sin desvío): sección de UC <br/>  Llamadas RTC (sin desvío): sección de puerta de enlace <br/>  Otros tipos de llamada <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas por tipo.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Volumen de llamadas (llamada inalámbrica)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión inalámbrica.  <br/> |
|**Volumen de llamadas (llamada VPN)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión VPN.  <br/> |
|**Volumen de llamadas (llamada externa)** <br/> |No  <br/> |Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |No  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.  <br/> |
|**Degradación (MOS)** <br/> |No  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype para un conjunto de algoritmos de Business Server predecir cómo los usuarios habría calificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |No  <br/> |Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |No  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |No  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |No  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
   
**Métricas de informe de resumen de calidad Media: Resumen de videollamada**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada/tipo de extremo** <br/> |No  <br/> | Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son: <br/>  Llamadas de punto a punto de UC <br/>  Sesiones de conferencia de UC <br/>  Sesiones de conferencia de RTC <br/>  Llamadas RTC: desvío de medios <br/>  Llamadas RTC (sin desvío): sección de UC <br/>  Llamadas RTC (sin desvío): sección de puerta de enlace <br/>  Otros tipos de llamada <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas por tipo.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Volumen de llamadas (llamada inalámbrica)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión inalámbrica.  <br/> |
|**Volumen de llamadas (llamada VPN)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión VPN.  <br/> |
|**Volumen de llamadas (llamada externa)** <br/> |No  <br/> |Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.  <br/> |
|**Velocidad de bits media (Kbits/s)** <br/> |No  <br/> |Velocidad de bits de vídeo media (en kilobits por segundo).  <br/> |
|**% de velocidad de bits baja** <br/> |No  <br/> |Porcentaje de la llamada con una velocidad de bits baja.  <br/> |
|**Pérdida de paquetes de salida** <br/> |No  <br/> |Pérdida de paquetes del Protocolo de transporte en tiempo real (RTP) correspondiente a los paquetes salientes (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**% fotogramas congelados** <br/> |No  <br/> |Porcentaje de tramas "inmovilizadas". En un fotograma congelado, el vídeo detiene su avance mientras que la parte de audio de la llamada continúa.  <br/> |
|**Velocidad de fotogramas media de salida** <br/> |No  <br/> |Velocidad de fotogramas media para las transmisiones de salida durante la llamada.  <br/> |
|**Velocidad de fotogramas media de entrada** <br/> |No  <br/> |Velocidad de fotogramas media para las transmisiones de entrada durante la llamada.  <br/> |
|**% de velocidad de fotogramas baja de entrada** <br/> |No  <br/> |Porcentaje de la llamada con una velocidad de bits baja para el vídeo de entrada.  <br/> |
|**% de estado del cliente** <br/> ||Indica el estado relativo del dispositivo cliente durante la llamada.  <br/> |
   
**Métricas de informe de resumen de calidad Media: Aplicación llamada resumen de compartir**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada/tipo de extremo** <br/> |No  <br/> | Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son: <br/>  Llamadas de punto a punto de UC <br/>  Sesiones de conferencia de UC <br/>  Sesiones de conferencia de RTC <br/>  Llamadas RTC: desvío de medios <br/>  Llamadas RTC (sin desvío): sección de UC <br/>  Llamadas RTC (sin desvío): sección de puerta de enlace <br/>  Otros tipos de llamada <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas por tipo.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Volumen de llamadas (llamada inalámbrica)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión inalámbrica.  <br/> |
|**Volumen de llamadas (llamada VPN)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión VPN.  <br/> |
|**Volumen de llamadas (llamada externa)** <br/> |No  <br/> |Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Unidireccional relativo medio** <br/> |No  <br/> |Retraso unidireccional relativo medio entre dos extremos de medios. Es una medición de la latencia de un solo salto.  <br/> |
|**Latencia media de procesamiento de iconos RDP** <br/> |No  <br/> |La latencia media de procesamiento de iconos RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Una media alta refleja un retraso mayor en la experiencia de visualización e incluye latencia de red. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.  <br/> |
|**% total de iconos dañados** <br/> |No  <br/> |Porcentaje total de iconos RDP dañados.  <br/> |
   

