---
title: Informe de rendimiento del servidor en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 'Resumen: Obtenga información sobre el informe rendimiento del servidor de Skype empresarial Server.'
ms.openlocfilehash: c2956910384c1e48fc9d38a9084bf1a4afe48539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279791"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>Informe de rendimiento del servidor en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de rendimiento del servidor en Skype empresarial Server.
  
El informe de rendimiento del servidor proporciona una lista de servidores de Skype empresarial que han experimentado el porcentaje más alto de llamadas inadecuadas. El informe desglosa los servidores por tipo de servidor y notifica diferentes estadísticas para los siguientes tipos:
  
- Servidor de mediación
    
- Servidor de conferencia A/V
    
- Servidor perimetral A/V
    
- Puerta de enlace (servidor de mediación)
    
- Puerta de enlace (desvío del servidor de mediación)
    
- Vídeo (incluye métricas de vídeo para servidores de conferencia A/V y servidores perimetrales A/V)
    
- Uso compartido de aplicaciones (incluye métricas de uso compartido de aplicaciones para servidores de conferencia A/V y servidores perimetrales A/V)
    
Es importante tener en cuenta que la clasificación mostrada en este informe como clasificaciones relativas. Por ejemplo, supongamos que el servidor con el peor rendimiento tuvo una llamada deficiente entre las 1000 llamadas realizadas. Eso supone un porcentaje más que aceptable del 0,1 %. Pero, si es el servidor de peor rendimiento (es decir, todos los demás servidores tienen un porcentaje de llamadas deficientes incluso inferior al 0,1 %), aparecerá en el informe de rendimiento del servidor.
  
## <a name="accessing-the-server-performance-report"></a>Acceso al informe de rendimiento del servidor

El informe de acceso del servidor es accesible desde la página principal de informes de supervisión. Puede explorar en profundidad el [Informe de la lista de llamadas en Skype empresarial Server](call-list-report-0.md) haciendo clic en una de las siguientes métricas:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
Además, puede navegar hasta el informe de tendencias de calidad de medios del servidor haciendo clic en las métricas siguientes:
  
- Tendencia
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>Optimización del uso del informe de rendimiento del servidor

El informe de rendimiento del servidor ofrece varias maneras de filtrar los datos; por ejemplo, puede filtrar por tipo de red (llamadas realizadas desde una conexión cableada frente a las llamadas realizadas desde una conexión inalámbrica) y tipo de acceso (llamadas realizadas desde dentro del firewall frente a las llamadas realizadas desde fuera del firewall). Para ver el informe de rendimiento del servidor, es buena idea utilizar estos filtros. Por ejemplo, supongamos que tiene un servidor de mediación con un porcentaje de llamadas deficientes del 3,24 %. Si solo consulta las llamadas inalámbricas, el mismo servidor podría tener un porcentaje de llamadas deficientes cercano al 20 %. Eso significa que el servidor tenía dificultades con las llamadas inalámbricas, un problema que quedó oculto en parte porque el servidor no tenía problemas con las llamadas cableadas.
  
## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o para ver los datos devueltos de diversas formas. Por ejemplo, el informe de rendimiento del servidor permite realizar tareas como filtrar los datos devueltos por el tipo de servidor o por el tipo de red (con cable o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la siguiente tabla se muestran los filtros que se pueden usar en el informe de rendimiento del servidor.
  
**Filtros del informe de rendimiento del servidor**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Tipo de servidor** <br/> |Indica el tipo de servidor cuyo rendimiento necesita notificarse. Seleccione una de las opciones siguientes:  <br/> Las Servidor de mediación de conferencia A/V servidor perimetral A/V |
|**Superior N** <br/> |Indica la cantidad de servidores (en función de su escaso porcentaje de llamadas) que se va a mostrar en cada categoría. Por ejemplo, si selecciona **5**, aparecerán los cinco servidores con peor rendimiento. Seleccione una de las opciones siguientes:<br/> [All] 5 10 |
|**Tipo de acceso** <br/> |Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> Las Externa interna |
|**Tipo de red** <br/> |Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:  <br/> Las Cable inalámbrico |
|**VPN** <br/> |Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> Las VPN sin VPN |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de rendimiento del servidor.
  
**Métricas del informe de rendimiento del servidor: resumen de llamadas de audio**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Servidor** <br/> |No  <br/> |Nombre/dirección IP del servidor.  <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas realizadas.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |Sí  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**Degradación (MOS)** <br/> |Sí  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype empresarial Server, el servidor de supervisión usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |Sí  <br/> |Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |Sí  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |Sí  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |Sí  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |Sí  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
   
**Métricas del informe de rendimiento del servidor: resumen de llamadas de vídeo**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada/tipo de extremo** <br/> |No  <br/> | Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son: <br/>  Llamadas de punto a punto de UC <br/>  Sesiones de conferencia de UC <br/>  Sesiones de conferencia de RTC <br/>  Llamadas RTC: desvío de medios <br/>  Llamadas RTC (sin desvío): sección de UC <br/>  Llamadas RTC (sin desvío): sección de puerta de enlace <br/>  Otros tipos de llamada <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas por tipo.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Volumen de llamadas (llamada inalámbrica)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión inalámbrica.  <br/> |
|**Volumen de llamadas (llamada VPN)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión VPN.  <br/> |
|**Volumen de llamadas (llamada externa)** <br/> |No  <br/> |Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.  <br/> |
|**Velocidad de bits media (Kbits/s)** <br/> |No  <br/> |Velocidad de bits de vídeo media (en kilobits por segundo).  <br/> |
|**% de velocidad de bits baja** <br/> |No  <br/> |Porcentaje de la llamada con una velocidad de bits baja.  <br/> |
|**Pérdida de paquetes de salida** <br/> |No  <br/> |Pérdida de paquetes de salida del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes de RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Las altas tasas de pérdidas suelen estar causadas por congestión, falta de ancho de banda, congestión inalámbrica o interferencias, o un servidor de medios sobrecargado. La pérdida de paquetes suele producir distorsión o pérdida de audio.  <br/> |
|**% fotogramas congelados** <br/> |No  <br/> |Porcentaje de fotogramas "inmovilizados". En un fotograma congelado, el vídeo detiene su avance mientras que la parte de audio de la llamada continúa.  <br/> |
|**Velocidad de fotogramas media de salida** <br/> |No  <br/> |Velocidad de fotogramas media para las transmisiones de salida durante la llamada.  <br/> |
|**Velocidad de fotogramas media de entrada** <br/> |No  <br/> |Velocidad de fotogramas media para las transmisiones de entrada durante la llamada.  <br/> |
|**% de velocidad de fotogramas baja de entrada** <br/> |No  <br/> |Porcentaje de la llamada con una velocidad de bits baja para el vídeo de entrada.  <br/> |
|**% de estado del cliente** <br/> ||Indica el estado relativo del dispositivo cliente durante la llamada.  <br/> |
   
**Métricas del informe de rendimiento del servidor: resumen de llamadas de uso compartido de aplicaciones**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada/tipo de extremo** <br/> |No  <br/> | Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son: <br/>  Llamadas de punto a punto de UC <br/>  Sesiones de conferencia de UC <br/>  Sesiones de conferencia de RTC <br/>  Llamadas RTC: desvío de medios <br/>  Llamadas RTC (sin desvío): sección de UC <br/>  Llamadas RTC (sin desvío): sección de puerta de enlace <br/>  Otros tipos de llamada <br/> |
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas por tipo.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Volumen de llamadas (llamada inalámbrica)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión inalámbrica.  <br/> |
|**Volumen de llamadas (llamada VPN)** <br/> |No  <br/> |Cantidad total de llamadas que ha empleado una conexión VPN.  <br/> |
|**Volumen de llamadas (llamada externa)** <br/> |No  <br/> |Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Unidireccional relativo medio** <br/> |No  <br/> |Retraso unidireccional relativo medio entre dos extremos de medios. Es una medición de la latencia de un solo salto.  <br/> |
|**Latencia media de procesamiento de iconos RDP** <br/> |No  <br/> |Latencia media de procesamiento de iconos RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Esta métrica no incluye la latencia de red. Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.  <br/> |
|**% total de iconos dañados** <br/> |No  <br/> |Porcentaje total de iconos RDP dañados.  <br/> |
   

