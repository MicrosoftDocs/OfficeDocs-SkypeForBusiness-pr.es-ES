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
description: 'Resumen: obtenga información sobre el informe de voz y vídeo punto a punto en Skype Empresarial Server.'
ms.openlocfilehash: 7e07c5778f43c3a0cac4ff162ed3d7dd1108eb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816620"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Informe de voz y vídeo punto a punto en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de voz y vídeo punto a punto en Skype Empresarial Server.
  
El informe de voz y vídeo punto a punto proporciona una vista detallada de la distribución de las llamadas de voz y vídeo durante un período de tiempo especificado (por ejemplo, llamadas por hora o llamadas por día). El informe también le ofrece la opción de ver todas las llamadas de voz y vídeo realizadas, o de ver solo las llamadas correctas o con errores. Los informes muestran información de llamadas desglosada en las siguientes agrupaciones:
  
- Llamadas por grupo
    
- Llamadas por tipo de llamada (por ejemplo, una llamada de Skype Empresarial a Skype Empresarial frente a una llamada de Skype Empresarial a una persona de la red RTC)
    
- Llamadas por tipo de acceso (usuarios que iniciaron sesión en la red interna frente a usuarios que iniciaron sesión en la red externa)
    
- Llamadas por servidor de mediación
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para obtener acceso al informe de voz y vídeo punto a punto

Solo puede obtener acceso al informe de voz y vídeo punto a punto abriendo el informe de resumen de actividad punto a punto y, a continuación, haciendo clic en cualquiera de las métricas siguientes:
  
- Total de sesiones de audio punto a punto
    
- Total de minutos de audio punto a punto
    
- Total de sesiones de vídeo punto a punto
    
- Total de minutos de vídeo punto a punto
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para aprovechar al máximo el informe de voz y vídeo punto a punto

Hay varias maneras de filtrar el informe de voz y vídeo punto a punto. Sin embargo, estas opciones de filtrado están ocultas de la vista de forma predeterminada. Para ver las opciones de filtrado disponibles, haga clic en el botón Mostrar **u** ocultar parámetros en la esquina superior derecha de la ventana Informe.
  
## <a name="filters"></a>Filtros

Los filtros proporcionan una forma de devolver un conjunto de datos más específico o de ver los datos de diferentes maneras. En la tabla siguiente se enumeran los filtros que puede usar con el informe de voz y vídeo punto a punto.
  
**Filtros de informes de voz y vídeo punto a punto**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
|**Tipo de medio** <br/> | Indica el tipo de medio usado en la sesión. Seleccione una de las siguientes opciones: <br/>  Ambas <br/>  Audio <br/>  Vídeo <br/> |
|**Eliminación de llamadas** <br/> | Indica el éxito o fracaso de la sesión. Seleccione una de las siguientes opciones: <br/>  [Todos] <br/>  Llamadas correctas <br/>  Llamadas con errores <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de sesiones <br/>  Minutos de llamada <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas de actividad de voz y vídeo punto a punto por grupo

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada grupo de servidores.
  
**Métricas para la actividad de voz y vídeo punto a punto por grupo**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Grupo** <br/> |No  <br/> |Nombre del grupo de registradores o del servidor perimetral usado para la llamada.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas para la actividad de voz y vídeo punto a punto por tipo de llamada

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de llamada realizada.
  
**Métricas para la actividad de voz y vídeo punto a punto por tipo de llamada**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada** <br/> |No  <br/> | Indica el tipo de llamada que se realizó. Los valores son uno de los siguientes: <br/>  UC a UC <br/>  UC a RTC <br/>  RTC a UC <br/>  RTC a RTC <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas para la actividad de voz y vídeo punto a punto por tipo de acceso

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de acceso de red.
  
**Métricas para la actividad de voz y vídeo punto a punto por tipo de acceso**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de actividad** <br/> |No  <br/> | Indica si los clientes iniciaron sesión en la red interna o en la red externa cuando se llamó. Los valores suelen ser los siguientes: <br/>  Interno <br/>  Externo <br/>  Mixtos <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas de actividad de voz y vídeo punto a punto por servidor de mediación

En la tabla siguiente se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada servidor de mediación.
  
**Métricas de actividad de voz y vídeo punto a punto por servidor de mediación**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Servidor de mediación** <br/> |No  <br/> |Nombre del servidor de mediación.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Período de fecha y hora en el que se realizó la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Número total de sesiones o recuento total de mensajes.  <br/> |
   

