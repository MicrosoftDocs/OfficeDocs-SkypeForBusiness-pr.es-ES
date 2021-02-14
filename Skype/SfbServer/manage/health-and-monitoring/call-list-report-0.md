---
title: Informe de lista de llamadas en Skype Empresarial Server
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
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Resumen: obtenga información sobre el informe de lista de llamadas usado en Skype Empresarial Server.'
ms.openlocfilehash: 8deb14cc8d2b8ff4b47701502de414d7460a81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817080"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Informe de lista de llamadas en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de lista de llamadas usado en Skype Empresarial Server.
  
El informe de lista de llamadas proporciona métricas de calidad de la experiencia (QoE) para las llamadas individuales realizadas y recibidas en su organización. Tenga en cuenta que las métricas reales notificadas dependerán de cómo tenga acceso al informe de lista de llamadas. Por ejemplo, si abre el informe desde el informe de dispositivos en Skype Empresarial [Server,](device-report.md)verá métricas como las siguientes, que también se notifican en el informe de dispositivos:
  
- Micrófono del autor de la llamada
    
- Altavoz del autor de la llamada
    
- Micrófono del destinatario de la llamada
    
- Orador del destinatario de la llamada
    
- Relación de tiempo de conmutación de voz 
    
Sin embargo, si abre el informe de lista de llamadas desde el informe de ubicación en [Skype Empresarial Server,](location-report.md)no verá ninguna de estas métricas; en su lugar, verá métricas como estas:
  
- Recorrido de ida y vuelta (ms)
    
- Degradación (MOS)
    
- Pérdida de paquetes
    
- Vibración (ms)
    
Estas son las métricas que se notifican en el informe de ubicación. Sin embargo, en el Informe de lista de llamadas siempre puede hacer clic en la métrica Detalle para proporcionar información completa de QoE para cualquier llamada.
  
## <a name="accessing-the-call-list-report"></a>Acceso al informe de lista de llamadas

Se puede tener acceso al informe de lista de llamadas desde cualquiera de los siguientes informes:
  
- Informe [de ubicación en Skype Empresarial Server](location-report.md) (haciendo clic en la métrica Volumen de llamadas o Porcentaje de llamadas deficientes)
    
- Informe [de dispositivos en Skype Empresarial Server](device-report.md) (haciendo clic en la métrica Volumen de llamadas o Porcentaje de llamadas deficientes)
    
- Informe [de resumen de calidad de medios en Skype Empresarial Server](summary.md) (haciendo clic en la métrica Volumen de llamadas o Porcentaje de llamadas deficientes)
    
- Informe [de rendimiento del servidor en Skype Empresarial Server](server-performance.md) (haciendo clic en la métrica Volumen de llamadas o Porcentaje de llamadas deficientes)
    
Desde el informe de lista de llamadas, puede obtener acceso al Informe de detalles de llamadas en [Skype Empresarial Server](call-detail-report.md) haciendo clic en la métrica Detalles.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Aprovechar al máximo el informe de lista de llamadas

Si no recuerda qué miden realmente algunas de las métricas del informe de lista de llamadas (como el tiempo de conmutación de voz de relación), mantenga el mouse sobre la etiqueta de la métrica; A continuación, aparecerá una información sobre herramientas con una breve descripción de la métrica.
  
## <a name="filters"></a>Filtros

Ninguno. No puede filtrar el informe de lista de llamadas.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de lista de llamadas para cada llamada.
  
**Métricas del informe de lista de llamadas**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Detalles** <br/> |No  <br/> |Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.  <br/> |
|**Caller** <br/> |Sí  <br/> |Dirección SIP de la persona que inició la llamada.  <br/> |
|**Destinatario de la llamada** <br/> |Sí  <br/> |Dirección SIP de la persona a la que se llamó.  <br/> |
|**Hora de inicio** <br/> |Sí  <br/> |Fecha y hora en que se inició la llamada.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en que finalizó la llamada.  <br/> |
|**Agente de usuario de autor de la llamada** <br/> |Sí  <br/> |Software usado por el punto de conexión de la persona que inició la llamada.  <br/> |
|**Agente de usuario de destinatario de la llamada** <br/> |Sí  <br/> |Software usado por el punto de conexión de la persona a la que se llamó.  <br/> |
|**Recorrido de ida y vuelta (ms)** <br/> |Sí  <br/> |Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.  <br/> |
|**Degradación (MOS)** <br/> |Sí  <br/> |Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Skype Empresarial Server, un conjunto de algoritmos predicen cómo los usuarios hubieran clasificado una llamada.  <br/> Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.  <br/> |
|**Pérdida de paquetes** <br/> |Sí  <br/> |Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**Vibración** <br/> |Sí  <br/> |Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. La vibración es una forma de medir la "inestabilidad" de una llamada. Los valores elevados de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras ocultas** <br/> |Sí  <br/> |Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**Tasa de recuperación de muestras extendidas** <br/> |Sí  <br/> |Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.  <br/> |
|**Tasa de recuperación de muestras comprimidas** <br/> |Sí  <br/> |Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.  <br/> |
|**Conectividad** <br/> |Sí  <br/> | Tipo de vínculo de comunicación inalámbrica. Por lo general, esto es uno de los siguientes: <br/>  Retransmisión <br/>  Directo <br/> |
   

