---
title: Informe de tendencias de calidad de medios de servidor en Skype Empresarial Server
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
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Resumen: obtenga información sobre el informe de tendencias de calidad de medios de servidor en Skype Empresarial Server.'
ms.openlocfilehash: 29be4d84103caa045e6f3ea2d3c5a215d9630ea5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814310"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Informe de tendencias de calidad de medios de servidor en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de tendencias de calidad de medios del servidor en Skype Empresarial Server.
  
El informe de tendencias de calidad de medios de servidor permite comparar gráficamente hasta cinco servidores según métricas de calidad de la experiencia, como volumen de llamadas, porcentaje de llamadas deficientes, pérdida de paquetes y vibración. De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Acceso al Informe de tendencias de calidad de medios de servidores

Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:
  
- [Informe de rendimiento del servidor en Skype Empresarial Server](server-performance.md) (haciendo clic en la métrica Tendencia)
    
- [Informe de detalles de llamadas en Skype Empresarial Server](call-detail-report.md) (haciendo clic en la métrica de servidor perimetral A/V. Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Uso óptimo del Informe de tendencias de calidad de medios de servidores

Al hacer clic en la métrica Tendencia en el Informe de rendimiento del servidor en [Skype Empresarial Server](server-performance.md) para un servidor específico, se abrirá el Informe de tendencias de calidad de medios del servidor. Sin embargo, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla. Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores. Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo. Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.
  
En los gráficos que muestra el informe de tendencias de calidad de medios de servidor, los puntos etiquetados Volumen de llamadas y Porcentaje de llamadas deficientes son vínculos rápidos; al hacer clic en un punto del gráfico se abrirá una instancia del informe de lista de llamadas en Skype Empresarial [Server](call-list-report-0.md) que muestra el total de llamadas (o llamadas deficientes) para el período de tiempo especificado.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.
  
**Filtros del Informe de tendencias de calidad de medios de servidores**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/8/2015 y una fecha de finalización del 28/9/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
|**Tipo de servidor** <br/> | Tipo de servidor que se usa en la llamada. Los valores permitidos son: <br/>  Servidor de mediación <br/>  Servidor de conferencia A/V <br/>  Servidor perimetral A/V <br/>  Puerta de enlace (servidor de mediación) <br/>  Puerta de enlace (desvío de servidor de mediación) <br/>  Servidor de conferencias AS <br/> |
|**Servidores** <br/> |Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.  <br/> |
|**Tipo de acceso** <br/> | Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son: <br/>  [Todos] <br/>  Cableado <br/>  Inalámbrica <br/> |
|**VPN** <br/> | Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son: <br/>  [Todos] <br/>  VPN <br/>  No VPN <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.
  
**Métricas del Informe de tendencias de calidad de medios de servidores**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de llamadas** <br/> |No  <br/> |Número total de llamadas.  <br/> |
|**Degradación (MOS)** <br/> |No  <br/> |Cantidad media de degradación de MOS (puntuación de opinión media) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0; un valor de 0,5 o menos constituye una degradación aceptable. Anteriormente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. Skype Empresarial Server usa un conjunto de algoritmos para predecir cómo los usuarios hubieran clasificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o un extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |No  <br/> |El número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |No  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales; a una configuración incorrecta del enrutamiento, o a una sobrecarga en el servidor de medios. Estos valores elevados causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**Pérdida de paquetes** <br/> |No  <br/> |Tasa media de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración (ms)** <br/> |No  <br/> |Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. La vibración es una forma de medir la "inestabilidad" de una llamada. Los valores elevados de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |No  <br/> |Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |No  <br/> |Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |No  <br/> |Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones, y esto da lugar a un audio acelerado o distorsionado.  <br/> |
   

