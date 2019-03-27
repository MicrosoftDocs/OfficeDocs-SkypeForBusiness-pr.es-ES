---
title: Peer-to-Peer informe de voz y vídeo en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Resumen: Conozca el Peer-to-Peer voz y vídeo informe en Skype para Business Server.'
ms.openlocfilehash: a4572d23a4c41ce423bdc96634ed8a3b9a9b1042
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897625"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Peer-to-Peer informe de voz y vídeo en Skype para Business Server
 
**Resumen:** Obtenga información sobre el Peer-to-Peer voz y vídeo informe en Skype para Business Server.
  
El Informe de voz y vídeo punto a punto da una visión detallada de la distribución de las llamadas de voz y de las videollamadas en un período de tiempo especificado (por ejemplo, llamadas por hora o llamadas por día). El informe también da la opción de visualizar todas las llamadas de voz y videollamadas que se efectuaron, o de visualizar únicamente las llamadas correctas o las erróneas. Los informes muestran la información de las llamadas desglosadas en las agrupaciones siguientes:
  
- Llamadas por grupo de servidores
    
- Llamadas por tipo (por ejemplo, un Skype para la empresa a Skype para llamada de negocio frente a un Skype para llamada de negocio a una persona en la red RTC)
    
- Llamadas por tipo de acceso (los usuarios que iniciaron sesión en la red interna comparados con los usuarios que iniciaron sesión en la red externa)
    
- Llamadas por servidor de mediación
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para obtener acceso al informe de voz y vídeo punto a punto

Obtenga acceso al informe de voz y vídeo punto a punto abriendo el Informe de resumen de actividad punto a punto y haciendo clic en una de las métricas siguientes:
  
- Total de sesiones de audio punto a punto
    
- Total de minutos de audio punto a punto
    
- Total de sesiones de vídeo punto a punto
    
- Total de minutos de vídeo punto a punto
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para sacar el máximo provecho del informe de voz y vídeo punto a punto

Existen varias formas de filtrar el informe de voz y vídeo punto a punto. No obstante, normalmente esas opciones de filtrado están ocultas a la vista. Para ver las opciones de filtrado que tiene disponibles, haga clic en el botón **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana del informe.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos de diferentes formas. En la siguiente tabla se enumeran los filtros que puede utilizar con el informe de voz y vídeo punto a punto.
  
**Filtros del informe de voz y vídeo punto a punto**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Tipo de medio** <br/> | Indica el tipo de medio utilizado en la sesión. Seleccione una de las siguientes opciones: <br/>  Both <br/>  Audio <br/>  Vídeo <br/> |
|**Disposición de llamada** <br/> | Indica el resultado de la sesión. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Llamadas correctas <br/>  Llamadas con error <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de sesiones <br/>  Minutos de la llamada <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas de actividad de voz y vídeo punto a punto por grupo

En la siguiente tabla se enumera la información provista en el Informe de voz y vídeo punto a punto para cada grupo.
  
**Métricas de actividad de voz y vídeo punto a punto por grupo**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Grupo de servidores** <br/> |No  <br/> |Nombre del grupo de registrador o servidor perimetral utilizado para la llamada.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha/hora en que se produjo la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas de actividad de voz y vídeo punto a punto por tipo de llamada

En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de llamada realizada.
  
**Métricas de actividad de voz y vídeo punto a punto por tipo de llamada**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de llamada** <br/> |No  <br/> | Indica el tipo de llamada que se realizó. Los valores son uno de los siguientes: <br/>  UC-a-UC <br/>  UC-a-PSTN <br/>  PSTN-a-UC <br/>  PSTN-a-PSTN <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha/hora en que se produjo la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas de actividad de voz y vídeo punto a punto por tipo de acceso

En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de acceso a la red.
  
**Métricas de actividad de voz y vídeo punto a punto por tipo de acceso**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de actividad** <br/> |No  <br/> | Indica si los clientes habían iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Generalmente, los valores son los siguientes: <br/>  Interna <br/>  Externa <br/>  Mixta <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha/hora en que se produjo la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas de actividad de voz y vídeo punto a punto por servidor de mediación

En la siguiente tabla se enumera la información proporcionada en el informe de vídeo y voz de punto a punto para cada servidor de mediación.
  
**Métricas de actividad de voz y vídeo punto a punto por servidor de mediación**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Servidor de mediación** <br/> |No  <br/> |Nombre del servidor de mediación.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha/hora en que se produjo la llamada.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   

