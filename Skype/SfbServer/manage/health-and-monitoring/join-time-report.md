---
title: Informe de tiempo de unión a conferencia en Skype Empresarial Server
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
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Resumen: obtenga información sobre el Informe de resumen de tiempo de unión a conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 4b8f82c543e8c4f43c6d902ed828ba83436bfc6228f361b9c2ef2c1f55bfb6fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276795"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Informe de tiempo de unión a conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el Informe de resumen de tiempo de unión a conferencia en Skype Empresarial Server.
  
El Resumen del tiempo de incorporación a la conferencia permite determinar cuánto tardan los usuarios en unirse a una conferencia. El informe muestra el tiempo de unión promedio (en milisegundos), así como un desglose que permite saber cuántos usuarios pudieron unirse a una conferencia en 2 o menos segundos, cuántos usuarios necesitaron entre 2 y 5 segundos para unirse a la conferencia, etc.
  
## <a name="accessing-the-conference-join-time-report"></a>Acceder al informe de tiempo de incorporación a la conferencia

Para obtener acceso al informe del tiempo de incorporación a la conferencia tiene que ir a la página principal de los informes de supervisión.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de tiempo de incorporación a la conferencia.
  
**Filtros del informe de tiempo de incorporación a la conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2015, los datos se muestran para los días 8/7/2015 de 12:00 a 9/7/2015 12:00 AM (es decir, un total de 31 días de valor de datos). <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Sesiones de conferencia** <br/> | Tipo de sesión. Los valores permitidos son: <br/>  [All] <br/>  Sesiones de foco (el enfoque es la directiva central y el administrador de estado para reuniones en línea y coordina todos los aspectos de una conferencia <br/>  Uso compartido de aplicaciones <br/>  Conferencia A/V <br/>  Si selecciona [Todo], aparecerá el tiempo de incorporación a la conferencia total en la parte superior del informe. Recuerde que estos totales son solo para conferencias programada con Microsoft Exchange o Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de tiempo de incorporación a la conferencia.
  
**Métricas del informe de tiempo de incorporación a la conferencia**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Date** <br/> El título real de esta métrica variará en función del intervalo seleccionado.  <br/> |No  <br/> |Fecha y hora en las que tuvo lugar la conferencia.  <br/> |
|**Total de sesiones** <br/> |No  <br/> |Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
|**Promedio (ms)** <br/> |No  <br/> |Promedio del tiempo (en milisegundos) que tardaron los participantes en unirse a la conferencia.  <br/> |
|**Sesiones \< 2 seconds, Volume** <br/> |No  <br/> |Número de participantes que pudieron unirse a la conferencia en menos de 2 segundos.  <br/> |
|**Sesiones \< 2 seconds, Percentage** <br/> |No  <br/> ||
|**Sesiones 2-5 segundos, Volumen** <br/> |No  <br/> |Número de participantes que tardaron entre 2 y 5 segundos en unirse a la conferencia.  <br/> |
|**Sesiones 2-5 segundos, Porcentaje** <br/> |No  <br/> |Porcentaje del número total de participantes que llamaron que tardaron entre 2 y 5 segundos en unirse a la conferencia.  <br/> |
|**Sesiones 5-10 segundos, Volumen** <br/> |No  <br/> |Número de participantes que tardaron entre 5 y 10 segundos en unirse a la conferencia.  <br/> |
|**Sesiones 5-10 segundos, Porcentaje** <br/> |No  <br/> |Porcentaje del número total de participantes que llamaron que tardaron entre 5 y 10 segundos en unirse a la conferencia.  <br/> |
|**Sesiones \> 10 segundos, Volumen** <br/> |No  <br/> |Número de participantes que necesitaron más de 10 segundos en unirse a la conferencia.  <br/> |
|**Sesiones \> 10 segundos, Porcentaje** <br/> |No  <br/> |Porcentaje del número total de participantes que necesitaron más de 10 segundos en unirse a la conferencia.  <br/> |
   

