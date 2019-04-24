---
title: Informe de errores principales en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Resumen: Información sobre el informe de errores principales en Skype para Business Server.'
ms.openlocfilehash: a2e8b0592e7525b1102d198de32643109304ed82
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198080"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Informe de errores principales en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de errores principales en Skype para Business Server.
  
El Informe de errores principales proporciona una presentación de los errores más frecuentes y las tendencias en el tiempo. Los errores se basan en una combinación de las dos métricas siguientes:
  
- **Id. de diagnóstico**. Identificador único (en forma de un encabezado de ms-diagnostics) que se adjunta a un mensaje SIP. Los Id. de diagnóstico proporcionan información útil para la solución de problemas relacionados con la llamada.
    
- **Código de respuesta**. Los códigos de respuesta se usan en las sesiones de comunicación SIP para responder a solicitudes SIP. Por ejemplo, supongamos que Ken envía la solicitud INVITE a Pilar Ackerman (es decir, supongamos que Ken Myer llama Pilar Ackerman). Si Pilar responde, su teléfono le enviará el código de respuesta 200 (OK), indicando al teléfono de Ken que Pilar ha respondido. El informe de errores más sólo incluye los códigos de respuesta que se han enviado en respuesta a un error de llamada; Skype para Business Server no realizar un seguimiento de todos los códigos de respuesta emitidos durante el transcurso de una llamada.
    
No solo se proporciona información de la cantidad total de sesiones donde se produjo un error, sino también de la cantidad total de usuarios a los que afectó el error.
  
## <a name="accessing-the-top-failures-report"></a>Acceso al Informe de errores principales

Desde la página Informes supervisión se obtiene acceso al Informe de errores principales. Al hacer clic en la métrica de sesiones notificado le llevará al [Informe de distribución de errores en Skype para Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Hacer el mejor uso del Informe de errores principales

El Informe de errores principales es inusual en un sentido: le permite filtrar a la vez hasta 5 Id. de diagnóstico. (Normalmente sólo puede filtrar en un elemento - como la dirección SIP de un usuario - a la vez.) Para filtrar en varios identificadores de diagnósticos, simplemente escriba cada identificador en el cuadro de los identificadores de diagnóstico, separando los identificadores con comas. (Si desea, puede dejar un espacio en blanco después de cada coma). Por ejemplo:
  
1011, 2412, 1033, 52116, 1008
  
Haga eso y solo aparecerán las llamadas erróneas que notificaron al menos uno de esos cinco Id. de diagnóstico.
  
Si coloca el mouse sobre un código de respuesta verá una información sobre herramientas que le indica el significado del código de respuesta en cuestión. Por ejemplo, si coloca el mouse sobre el código de respuesta 486 verá este mensaje:
  
No disponible aquí.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de errores más comunes le permite filtrar los datos en función de aspectos tales como el tipo de actividad (sesión punto a punto o sesión de conferencia) o por el código de respuesta SIP que acompañó a la sesión fallida. Es posible también elegir la forma en la que los datos necesitan agruparse. En este caso, los usos se agrupan por hora, día, semana o mes.
  
La siguiente tabla muestra los filtros que puede utilizar con el informe de errores más comunes.
  
**Filtros del informe de errores más comunes**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Tipo de actividad** <br/> | Tipo de actividad. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Punto a punto <br/>  Una conferencia <br/> |
|**Modalidad** <br/> |En este momento, la única opción disponible es **[Todos]**.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Categoría** <br/> | Tipo de error. Seleccione una de las siguientes opciones: <br/>  Error esperado e inesperado <br/>  Error inesperado <br/>  Un "error esperado" es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen. Un "error inesperado" es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera. De ser así, tal cosa se identificaría como un error inesperado. <br/> |
|**Código de respuesta** <br/> |Código de respuesta SIP enviado cuando la conferencia ha fallado. Escriba el código de respuesta en su totalidad, como por ejemplo:  <br/> 400  <br/> |
|**Id. de diagnóstico** <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de errores más comunes.
  
**Métricas del informe de errores más comunes**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |Sí  <br/> |Clasificación relativa basada en la cantidad de sesiones de las que se informa.  <br/> |
|**Sesiones notificadas** <br/> |Sí  <br/> |Cantidad total de sesiones con error basadas en el Id. de diagnóstico y en el código de respuesta SIP.  <br/> |
|**Usuarios afectados** <br/> |Sí  <br/> |Cantidad total de usuarios afectados por la sesión con error.  <br/> |
|**Información del error** <br/> |No  <br/> |Información detallada sobre el error, incluido el Id. de diagnóstico, el código de respuesta SIP y la descripción de los motivos por los que se produjo un error en la sesión.  <br/> |
|**Tendencia en el pasado** <br/> |No  <br/> |Gráfico de sesiones con error a lo largo del tiempo.  <br/> |
   

