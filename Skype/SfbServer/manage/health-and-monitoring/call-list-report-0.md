---
title: Informe de la lista de llamadas en Skype empresarial Server
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
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Resumen: Obtenga información sobre el informe de la lista de llamadas que se usa en Skype empresarial Server.'
ms.openlocfilehash: 3013dcce34804c7afb4c0d1ca7a211f8decf56ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818121"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Informe de la lista de llamadas en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de la lista de llamadas usado en Skype empresarial Server.
  
El informe de lista de llamadas proporciona métricas relativas a la calidad de la experiencia para las llamadas individuales realizadas y recibidas en su organización. Tenga en cuenta que las métricas reales que se incluyan dependerán de cómo obtenga acceso al informe de lista de llamadas. Por ejemplo, si abre el informe desde el [Informe de dispositivos en Skype empresarial Server](device-report.md), verá las métricas como las siguientes, que también se incluyen en el informe de dispositivos:
  
- Micrófono del autor de la llamada
    
- Altavoz del autor de la llamada
    
- Micrófono del destinatario de la llamada
    
- Altavoz del destinatario de la llamada
    
- Relación de tiempo de conmutación de voz 
    
Sin embargo, si abre el informe de la lista de llamadas desde el [Informe de ubicación en Skype empresarial Server](location-report.md), no verá ninguna de esas métricas; en su lugar, verás métricas como las siguientes:
  
- Recorrido de ida y vuelta (ms)
    
- Degradación (MOS)
    
- Pérdida de paquetes
    
- Vibración (ms)
    
Esas son las métricas incluidas en el informe de ubicaciones. No obstante, siempre puede hacer clic en la métrica Detalles, en el informe de lista de llamadas, para obtener información completa sobre la calidad de la experiencia de cualquier llamada.
  
## <a name="accessing-the-call-list-report"></a>Acceso al informe de lista de llamadas

El informe de lista de llamadas es accesible desde cualquiera de los siguientes informes:
  
- El [Informe de ubicación en Skype empresarial Server](location-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)
    
- El [Informe del dispositivo en Skype empresarial Server](device-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)
    
- El [informe Resumen de calidad de medios en Skype empresarial Server](summary.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)
    
- El [Informe rendimiento del servidor de Skype empresarial Server](server-performance.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)
    
Desde el informe de la lista de llamadas puede acceder al [Informe de detalles de llamadas en Skype empresarial Server](call-detail-report.md) haciendo clic en la métrica de detalles.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Optimización del uso del informe de lista de llamadas

Si no recuerda qué miden algunas de las métricas del informe de lista de llamadas (por ejemplo, Relación de tiempo de conmutación de voz), mantenga el mouse sobre la etiqueta de la métrica y aparecerá una información sobre la herramienta con una breve descripción de la métrica.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de lista de llamadas.
  
## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información facilitada en el informe de lista de llamadas para cada llamada.
  
**Métricas del informe de lista de llamadas**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Detalles** <br/> |No  <br/> |Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.  <br/> |
|**Autor de llamada** <br/> |Sí  <br/> |Dirección SIP de la persona que inició la llamada.  <br/> |
|**Destinatario de la llamada** <br/> |Sí  <br/> |Dirección SIP de la persona que recibió la llamada.  <br/> |
|**Hora de inicio** <br/> |Sí  <br/> |Fecha y hora en que se inició la llamada.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en que finalizó la llamada.  <br/> |
|**Agente de usuario de autor de la llamada** <br/> |Sí  <br/> |Software utilizado por el extremo de la persona que inició la llamada.  <br/> |
|**Agente de usuario de destinatario de la llamada** <br/> |Sí  <br/> |Software utilizado por el extremo de la persona que recibió la llamada.  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |Sí  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.  <br/> |
|**Degradación (MOS)** <br/> |Sí  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype empresarial Server, un conjunto de algoritmos predice cómo los usuarios habrían calificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |Sí  <br/> |Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración** <br/> |Sí  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |Sí  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |Sí  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |Sí  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
|**Conectividad** <br/> |Sí  <br/> | Tipo de vínculo de comunicación inalámbrica. Normalmente es uno de los siguientes: <br/>  Retransmisión <br/>  Directo <br/> |
   

