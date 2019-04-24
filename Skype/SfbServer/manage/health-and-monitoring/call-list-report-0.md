---
title: Informe de lista de llamadas en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Resumen: Información sobre el informe de lista de llamadas usadas en Skype para Business Server.'
ms.openlocfilehash: c79cee289d3e76c0b191bb62a0383269ef8b886b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199760"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Informe de lista de llamadas en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de lista de llamadas usadas en Skype para Business Server.
  
El informe de lista de llamadas proporciona métricas relativas a la calidad de la experiencia para las llamadas individuales realizadas y recibidas en su organización. Tenga en cuenta que las métricas reales que se incluyan dependerán de cómo obtenga acceso al informe de lista de llamadas. Por ejemplo, si el informe se abre desde el [Informe de dispositivos en Skype para Business Server](device-report.md), verá las métricas como el siguiente, las métricas que también se notifican en el informe de dispositivos:
  
- Micrófono del autor de la llamada
    
- Altavoz del autor de la llamada
    
- Micrófono del destinatario de la llamada
    
- Altavoz del destinatario de la llamada
    
- Relación de tiempo de conmutación de voz 
    
Sin embargo, si abre el informe de lista de llamadas desde el [Informe de ubicación en Skype para Business Server](location-report.md), no verá ninguna de estas métricas; en su lugar, verá las siguientes:
  
- Recorrido de ida y vuelta (ms)
    
- Degradación (MOS)
    
- Pérdida de paquetes
    
- Vibración (ms)
    
Esas son las métricas incluidas en el informe de ubicaciones. No obstante, siempre puede hacer clic en la métrica Detalles, en el informe de lista de llamadas, para obtener información completa sobre la calidad de la experiencia de cualquier llamada.
  
## <a name="accessing-the-call-list-report"></a>Acceso al informe de lista de llamadas

El informe de lista de llamadas es accesible desde cualquiera de los siguientes informes:
  
- El [Informe de ubicación en Skype para Business Server](location-report.md) (haciendo clic en la métrica de porcentaje de llamadas deficientes o volumen de llamadas)
    
- El [Informe de dispositivos en Skype para Business Server](device-report.md) (haciendo clic en la métrica de porcentaje de llamadas deficientes o volumen de llamadas)
    
- El [Informe de resumen de calidad de medios en Skype para Business Server](summary.md) (haciendo clic en la métrica de porcentaje de llamadas deficientes o volumen de llamadas)
    
- El [Informe de rendimiento del servidor en Skype para Business Server](server-performance.md) (haciendo clic en la métrica de porcentaje de llamadas deficientes o volumen de llamadas)
    
Desde el informe de lista de llamadas, puede acceder al [Informe de detalles de llamadas en Skype para Business Server](call-detail-report.md) haciendo clic en la métrica detalles.
  
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
|**Degradación (MOS)** <br/> |Sí  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype para Business Server, un conjunto de algoritmos de predecir cómo los usuarios habría calificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |Sí  <br/> |Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración** <br/> |Sí  <br/> |Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |Sí  <br/> |Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |Sí  <br/> |Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |Sí  <br/> |Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
|**Conectividad** <br/> |Sí  <br/> | Tipo de vínculo de comunicación inalámbrica. Normalmente es uno de los siguientes: <br/>  Retransmisión <br/>  Directo <br/> |
   

