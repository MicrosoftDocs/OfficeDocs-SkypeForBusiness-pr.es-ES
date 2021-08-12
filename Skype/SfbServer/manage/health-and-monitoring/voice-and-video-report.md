---
title: Informe de voz y vídeo punto a punto en Skype Empresarial Server
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
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Summary: Learn about the Peer-to-Peer Voice and Video Report in Skype Empresarial Server.'
ms.openlocfilehash: 66d121965d7046a823e26bff8a14fba6ce8213690fcaa4a21ab7a31f4db9f904
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324329"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Informe de voz y vídeo punto a punto en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de voz y vídeo punto a punto en Skype Empresarial Server.
  
El informe de voz y vídeo punto a punto proporciona una vista detallada de la distribución de llamadas de voz y vídeo durante un período de tiempo especificado (por ejemplo, llamadas por hora o llamadas por día). El informe también le ofrece la opción de ver todas las llamadas de voz y vídeo realizadas, o de ver solo las llamadas correctas o con errores. Los informes muestran información de llamadas desglosada en las siguientes agrupaciones:
  
- Llamadas por grupo
    
- Llamadas por tipo de llamada (por ejemplo, una Skype Empresarial para Skype Empresarial frente a una Skype Empresarial llamada a una persona en la red RTC)
    
- Llamadas por tipo de acceso (usuarios que iniciaron sesión en la red interna frente a usuarios que iniciaron sesión en la red externa)
    
- Llamadas por servidor de mediación
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para obtener acceso al informe de voz y vídeo punto a punto

Solo puede obtener acceso al informe de voz y vídeo punto a punto abriendo el Informe de resumen de actividad punto a punto y, a continuación, haciendo clic en cualquiera de las siguientes métricas:
  
- Total de sesiones de audio punto a punto
    
- Total de minutos de audio punto a punto
    
- Total de sesiones de vídeo punto a punto
    
- Total de minutos de vídeo punto a punto
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para aprovechar al máximo el informe de voz y vídeo punto a punto

Hay varias formas de filtrar el informe de voz y vídeo punto a punto. Sin embargo, estas opciones de filtrado están ocultas de la vista de forma predeterminada. Para ver las opciones de filtrado disponibles, haga clic en el botón **Mostrar u** ocultar parámetros de la esquina superior derecha de la ventana Informe.
  
## <a name="filters"></a>Filtros

Los filtros proporcionan una forma de devolver un conjunto de datos más específico o de ver los datos de diferentes maneras. En la tabla siguiente se enumeran los filtros que puede usar con el informe de voz y vídeo punto a punto.
  
**Filtros de informes de voz y vídeo punto a punto**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2015, los datos se muestran para los días 8/7/2015 de 12:00 a 9/7/2015 12:00 AM (es decir, un total de 31 días de valor de datos). <br/> |
|**Tipo de medio** <br/> | Indica el tipo de medio usado en la sesión. Seleccione una de las siguientes opciones: <br/>  Ambas <br/>  Audio <br/>  Vídeo <br/> |
|**Eliminación de llamadas** <br/> | Indica el éxito o error de la sesión. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  Llamadas correctas <br/>  Llamadas con errores <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de sesiones <br/>  Minutos de llamadas <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas de actividad de voz y vídeo punto a punto por grupo

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada grupo.
  
**Métricas de actividad de voz y vídeo punto a punto por grupo**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Grupo** <br/> |No  <br/> |Nombre del grupo de registradores o servidor perimetral usado para la llamada.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas de actividad de voz y vídeo punto a punto por tipo de llamada

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de llamada realizada.
  
**Métricas de actividad de voz y vídeo punto a punto por tipo de llamada**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Tipo de llamada** <br/> |No  <br/> | Indica el tipo de llamada que se realizó. Los valores son uno de los siguientes: <br/>  UC a UC <br/>  UC a RTC <br/>  RTC a UC <br/>  RTC a RTC <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas de actividad de voz y vídeo punto a punto por tipo de acceso

En la tabla siguiente se muestra la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de acceso de red.
  
**Métricas de actividad de voz y vídeo punto a punto por tipo de acceso**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Tipo de actividad** <br/> |No  <br/> | Indica si los clientes iniciaron sesión en la red interna o en la red externa cuando se inició la llamada. Los valores suelen ser los siguientes: <br/>  Interno <br/>  Externo <br/>  Mixtos <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas de actividad de voz y vídeo punto a punto por el servidor de mediación

En la tabla siguiente se muestra la información proporcionada en el Informe de voz y vídeo punto a punto para cada servidor de mediación.
  
**Métricas de actividad de voz y vídeo punto a punto por el servidor de mediación**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Servidor de mediación** <br/> |No  <br/> |Nombre del servidor de mediación.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   

