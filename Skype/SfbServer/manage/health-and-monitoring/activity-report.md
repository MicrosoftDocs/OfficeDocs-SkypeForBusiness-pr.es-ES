---
title: Informe de actividad de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumen: Información sobre el informe de actividad de conferencia usadas en Skype para Business Server.'
ms.openlocfilehash: 09ad67452c9c24aff8e0f67998b654ade8d929fd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879521"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Informe de actividad de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de actividad de conferencia usadas en Skype para Business Server.
  
El informe de actividad de conferencia le facilita que responda a preguntas como cuántas conferencias se están celebrando cada día y cuántas se celebran. La información como esta no es solo útil por sí misma sino también como herramienta de solución de problemas. Por ejemplo, supongamos que los usuarios se están quejando de que la red parece particularmente lenta a mitad del día. Informes de un vistazo rápido a la actividad de conferencia, podrían sugerir uno de los motivos posible: se ha programado la mucho más conferencias entre las 10:00 A.M. y las 2:00 P.M., a continuación, en cualquier otro momento.
  
Si la red lenta está causando problemas, puede animar a los usuarios a reprogramar algunas de sus conferencias durante las horas de menor tráfico del día.
  
## <a name="accessing-the-conference-activity-report"></a>Acceso al informe de actividad de conferencia

El informe de actividad de conferencia se obtiene acceso desde el [Informe de resumen de conferencia en Skype para Business Server](conference-summary-report.md) haciendo clic en cualquiera de las siguientes métricas:
  
- Total de conferencias
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Aprovechar al máximo el informe de actividad de conferencia

De manera predeterminada, el informe de actividad de conferencia le muestra la cantidad total de conferencias para el período de tiempo especificado (por ejemplo, la cantidad total de conferencias por día o la cantidad total de conferencias por hora del día). Pero, puede elegir visualizar la cantidad total de participantes para ese período de tiempo o la cantidad total de minutos de participante. Para ello, haga clic en el botón Mostrar u ocultar parámetros para visualizar las opciones de filtrado y, luego, seleccione uno de los siguientes en la lista desplegable Informe por:
  
- Recuento de participantes
    
- Minutos de participantes
    
- Recuento de conferencias
    
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de actividad de conferencia.
  
**Filtros del informe de actividad de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de participantes <br/>  Minutos de participantes <br/>  Recuento de conferencias <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferencias por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada grupo.
  
**Métricas para conferencias por grupo**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Grupo de servidores** <br/> |No  <br/> |Nombre del grupo de registradores o servidor perimetral utilizado en la conferencia.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en que se desarrolló la conferencia.  <br/> |
|**Total** <br/> |No  <br/> |Recuento total de participantes, minutos totales por participante o recuento total de conferencias.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferencias por tipo de servidor

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada tipo de servidor.
  
**Métricas para conferencias por tipo de servidor**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferencia** <br/> |No  <br/> | Tipo de servidor usado en la conferencia, generalmente, uno de los siguientes: <br/>  Servidor de conferencia web <br/>  Servidor de conferencia de mensajería instantánea <br/>  Servidor de conferencia con telefonía <br/>  Servidor de conferencia A/V <br/>  Uso compartido de aplicaciones <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en que se desarrolló la conferencia.  <br/> |
|**Total** <br/> |No  <br/> |Recuento total de participantes, minutos totales por participante o recuento total de conferencias.  <br/> |
   

