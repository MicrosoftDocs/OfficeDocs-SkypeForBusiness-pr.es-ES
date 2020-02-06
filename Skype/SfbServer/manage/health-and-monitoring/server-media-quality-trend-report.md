---
title: Informe de tendencias de calidad de Media Server en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Resumen: Obtenga información sobre el informe de tendencia de calidad de Media Server en Skype empresarial Server.'
ms.openlocfilehash: eca6aa75d7b831356da15a86692658019b3c0d54
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817719"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Informe de tendencias de calidad de Media Server en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de tendencias de calidad de Media Server en Skype empresarial Server.
  
El Informe de tendencias de calidad de medios de servidores permite comparar de forma gráfica hasta cinco servidores según diversas métricas de Calidad de la experiencia, como volumen de llamadas, porcentaje de llamadas deficientes, pérdida de paquetes y vibración. De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Acceso al Informe de tendencias de calidad de medios de servidores

Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:
  
- [Informe de rendimiento del servidor en Skype empresarial Server](server-performance.md) (al hacer clic en la métrica de tendencia)
    
- [Informe de detalles de llamadas en Skype empresarial Server](call-detail-report.md) (haciendo clic en la métrica del servidor perimetral a/V). Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo).
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Uso óptimo del Informe de tendencias de calidad de medios de servidores

Al hacer clic en la métrica de tendencia en el [Informe rendimiento del servidor de Skype empresarial Server](server-performance.md) para un servidor específico, se abrirá el informe tendencia de calidad de medios de servidor. Pero, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla. Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores. Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo. Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.
  
En los gráficos que muestra el informe de tendencias de calidad de Media Server, se hotlinksn los puntos con la etiqueta llamada de volumen y bajo porcentaje de llamada. al hacer clic en un punto del gráfico, se abrirá una instancia del informe de la [lista de llamadas en Skype empresarial Server en](call-list-report-0.md) la que se muestran las llamadas totales (o llamadas deficientes) durante el período de tiempo especificado.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.
  
**Filtros del Informe de tendencias de calidad de medios de servidores**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/08/2015 y una fecha de finalización del 28/09/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Tipo de servidor** <br/> | Tipo de servidor que se usa en la llamada. Los valores permitidos son: <br/>  Servidor de mediación <br/>  Servidor de conferencia A/V <br/>  Servidor perimetral A/V <br/>  Puerta de enlace (servidor de mediación) <br/>  Puerta de enlace (desvío del servidor de mediación) <br/>  Servidor de conferencias AS <br/> |
|**Servidores** <br/> |Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.  <br/> |
|**Tipo de acceso** <br/> | Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son: <br/>  [Todas] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son: <br/>  [Todas] <br/>  Cableada <br/>  Inalámbrica <br/> |
|**VPN** <br/> | Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son: <br/>  [Todas] <br/>  VPN <br/>  Distinto de VPN <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.
  
**Métricas del Informe de tendencias de calidad de medios de servidores**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de llamadas** <br/> |No  <br/> |Cantidad total de llamadas.  <br/> |
|**Degradación (MOS)** <br/> |No  <br/> |Cantidad promedio de la degradación de OP (puntuación de opción media) experimentada durante una llamada. Los valores de degradación pueden oscilar entre un mínimo de 0,0 y un alto de 5,0. un valor de 0,5 o menos representa una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. Skype empresarial Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.  <br/> Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |No  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**Pérdida de paquetes** <br/> |No  <br/> |Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |No  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |No  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |No  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
   

