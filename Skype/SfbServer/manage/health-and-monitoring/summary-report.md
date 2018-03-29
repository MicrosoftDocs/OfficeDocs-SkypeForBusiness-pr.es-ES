---
title: Informe de resumen de diagnósticos de llamadas en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Resumen: Conozca llamar resumen informe de diagnósticos utilizados en Skype para Business Server 2015.'
ms.openlocfilehash: 8d040ab2d59fdbc822448de2d3c9918ec39ae289
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server-2015"></a>Informe de resumen de diagnósticos de llamadas en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre llamar resumen informe de diagnósticos utilizados en Skype para Business Server 2015.
  
El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:
  
- Mensajería instantánea
    
- Uso compartido de aplicaciones
    
- Transferencia de archivos
    
- Audio
    
- Vídeo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Acceso al informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión. Desde el informe de resumen de diagnóstico llame puede tener acceso el [informe de diagnóstico de actividad Peer-to-Peer de Skype para Business Server 2015](peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica de la tasa de error en la sección de resumen de la sesión de Peer-to-Peer del informe. También puede abrir el [Informe de diagnóstico de conferencia en Skype para Business Server 2015](conference-diagnostic-report.md) haciendo clic en cualquiera de las siguientes métricas de conferencia:
  
- Porcentaje de errores de sesión generales
    
- Porcentaje de errores de foco
    
- Porcentaje de errores de MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimización del uso del informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnóstico llame incluye gráficos que comparan las tasas de errores para las diversas modalidades utilizadas en Skype para Business Server 2015. Las columnas de estos gráficos son realmente vínculos activos; Por ejemplo, si hace clic en la columna de mensajería instantánea para la sesiones de peer-to-peer, podrá desglosar una instancia del [informe de diagnóstico de actividad Peer-to-Peer de Skype para Business Server 2015](peer-to-peer-activity-diagnostic-report.md), un informe que proporciona información adicional acerca de todas las las sesiones incluidas en el informe de resumen de diagnóstico llamar de mensajería instantánea.
  
## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos necesitan agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).
  
En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.
  
**Llamar a filtros de informe resumen de diagnóstico**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).
  
**Métricas para la sesiones de Peer-to-Peer**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de sesiones** <br/> |No  <br/> |Cantidad total de sesiones punto a punto que ha tenido lugar.  <br/> |
|**Porcentaje de errores** <br/> |No  <br/> |Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).
  
**Métricas para la sesiones de conferencia**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de conferencias** <br/> |No  <br/> |Cantidad total de conferencias que ha tenido lugar.  <br/> |
|**Total de sesiones de conferencias** <br/> |No  <br/> |Cantidad total de sesiones de conferencia que ha tenido lugar.  <br/> |
|**Porcentaje de errores de sesión generales** <br/> |No  <br/> |Porcentaje del total de sesiones de conferencia con errores.  <br/> |
|**Sesiones de foco** <br/> |No  <br/> |Cantidad total de las sesiones de conferencia basadas en foco con errores.  <br/> |
|**Porcentaje de errores de foco** <br/> |No  <br/> |Porcentaje de las sesiones de conferencia basadas en foco con errores.  <br/> |
|**Sesiones MCU** <br/> |No  <br/> |Cantidad total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.  <br/> |
|**Porcentaje de errores de MCU** <br/> |No  <br/> |Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.  <br/> |
   

