---
title: Informe de resumen de diagnóstico de llamadas en Skype Empresarial Server
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Summary: Learn about the Call Diagnostic Summary Report used in Skype Empresarial Server.'
ms.openlocfilehash: 35b6a9ac84bf504b218200ec2ac49e6f19632e520eba90335e9ab0257f4bcfcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281843"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Informe de resumen de diagnóstico de llamadas en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de resumen de diagnóstico de llamadas usado en Skype Empresarial Server.
  
El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:
  
- Mensajería instantánea
    
- Uso compartido de aplicaciones
    
- Transferencia de archivos
    
- Audio
    
- Vídeo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Acceso al informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión. En el Informe de resumen de diagnóstico de llamadas, puede obtener acceso al Informe de diagnóstico de actividad punto a punto en [Skype Empresarial Server](peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica Tasa de errores en la sección Resumen de sesión punto a punto del informe. También puede obtener acceso al Informe de diagnóstico de conferencia [en Skype Empresarial Server](conference-diagnostic-report.md) haciendo clic en cualquiera de las siguientes métricas de conferencia:
  
- Porcentaje de errores de sesión generales
    
- Porcentaje de errores de foco
    
- Porcentaje de errores de MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimización del uso del informe de resumen de diagnósticos de llamadas

El Informe de resumen de diagnóstico de llamadas incluye gráficos que comparan las tasas de errores para las distintas modalidades usadas en Skype Empresarial Server. Las columnas de estos gráficos son realmente hotlinks; por ejemplo, si hace clic en la columna Mensajería instantánea para sesiones punto a punto, profundizará en una instancia del Informe de diagnóstico de actividad punto a punto en [Skype Empresarial Server](peer-to-peer-activity-diagnostic-report.md), un informe que proporciona detalles adicionales sobre todas las sesiones de mensajería instantánea incluidas en el Informe de resumen de diagnóstico de llamadas.
  
## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos deben agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).
  
En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.
  
**Filtros del informe de resumen de diagnósticos de llamadas**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2015, los datos se muestran para los días 8/7/2015 de 12:00 a 9/7/2015 12:00 AM (es decir, un total de 31 días de valor de datos). <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).
  
**Métricas de las sesiones punto a punto**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Total de sesiones** <br/> |No  <br/> |Número total de sesiones punto a punto que ha tenido lugar.  <br/> |
|**Porcentaje de errores** <br/> |No  <br/> |Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).
  
**Métricas de las sesiones de conferencia**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Description**|
|:-----|:-----|:-----|
|**Total de conferencias** <br/> |No  <br/> |Número total de conferencias que ha tenido lugar.  <br/> |
|**Total de sesiones de conferencias** <br/> |No  <br/> |Número total de sesiones de conferencia que ha tenido lugar.  <br/> |
|**Porcentaje de errores de sesión generales** <br/> |No  <br/> |Porcentaje del total de sesiones de conferencia con errores.  <br/> |
|**Sesiones de foco** <br/> |No  <br/> |Número total de las sesiones de conferencia basadas en foco con errores.  <br/> |
|**Porcentaje de errores de foco** <br/> |No  <br/> |Porcentaje de las sesiones de conferencia basadas en foco con errores.  <br/> |
|**Sesiones MCU** <br/> |No  <br/> |Número total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.  <br/> |
|**Porcentaje de errores de MCU** <br/> |No  <br/> |Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.  <br/> |
   

