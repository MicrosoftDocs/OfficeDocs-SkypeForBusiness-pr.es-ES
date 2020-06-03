---
title: Informe de actividad de conferencia en Skype empresarial Server
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
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumen: Obtenga información sobre el informe de actividad de conferencia usado en Skype empresarial Server.'
ms.openlocfilehash: b9ea4112d144bff88ae72e5805d79f17e655d8f3
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "41818181"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Informe de actividad de conferencia en Skype empresarial Server
 
**Resumen:** Obtenga información sobre el informe de actividad de conferencia usado en Skype empresarial Server.
  
El informe de actividad de conferencia le facilita que responda a preguntas como cuántas conferencias se están celebrando cada día y cuántas se celebran. La información como esta no es solo útil por sí misma sino también como herramienta de solución de problemas. Por ejemplo, supongamos que los usuarios se están quejando de que la red parece particularmente lenta a mitad del día. Un vistazo rápido a los informes de actividad de conferencia puede sugerir una posible razón: muchas más conferencias se están programando entre las horas 10:00 A.M. y 2:00 P.M. después, en cualquier otro momento.
  
Si la red lenta está causando problemas, puede animar a los usuarios a reprogramar algunas de sus conferencias durante las horas de menor tráfico del día.
  
## <a name="accessing-the-conference-activity-report"></a>Acceso al informe de actividad de conferencia

Para obtener acceso al informe de actividad de conferencia desde el [Informe de Resumen de conferencia en Skype empresarial Server](conference-summary-report.md) , haga clic en una de las siguientes métricas:
  
- Total de conferencias
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Aprovechar al máximo el informe de actividad de conferencia

De manera predeterminada, el informe de actividad de conferencia le muestra el número total de conferencias para el período de tiempo especificado (por ejemplo, el número total de conferencias por día o el número total de conferencias por hora del día). Sin embargo, puede elegir visualizar el número total de participantes para ese período de tiempo o el número total de minutos de participante. Para ello, haga clic en el botón Mostrar u ocultar parámetros para visualizar las opciones de filtrado y, a continuación, seleccione uno de los siguientes en la lista desplegable Informe por:
  
- Recuento de participantes
    
- Minutos de participantes
    
- Recuento de conferencias
    
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de actividad de conferencia.
  
**Filtros del informe de actividad de conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre empiezan en domingo y terminan en sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2015 y una fecha de finalización de 2/28/2015, los datos se muestran para los días 8/7/2015 12:00 a 9/7/2015 12:00 A.M. (es decir, un total de 31 días de datos). <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de participantes <br/>  Minutos de participante <br/>  Recuento de conferencias <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferencias por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada grupo.
  
**Métricas para conferencias por grupo**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Grupo** <br/> |No  <br/> |Nombre del grupo de registradores o servidor perimetral utilizado en la conferencia.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en que se desarrolló la conferencia.  <br/> |
|**Total** <br/> |No  <br/> |Recuento total de participantes, minutos totales por participante o recuento total de conferencias.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferencias por tipo de servidor

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada tipo de servidor.
  
**Métricas para conferencias por tipo de servidor**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferencia** <br/> |No  <br/> | Tipo de servidor usado en la conferencia, generalmente, uno de los siguientes: <br/>  Servidor de conferencia web <br/>  Servidor de conferencia de mensajería instantánea <br/>  Servidor de conferencia con telefonía <br/>  Servidor de conferencia A/V <br/>  Uso compartido de aplicaciones <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en que se desarrolló la conferencia.  <br/> |
|**Total** <br/> |No  <br/> |Recuento total de participantes, minutos totales por participante o recuento total de conferencias.  <br/> |
   

