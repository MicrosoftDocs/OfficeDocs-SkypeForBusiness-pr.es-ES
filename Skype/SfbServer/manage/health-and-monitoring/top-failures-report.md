---
title: Informe de errores principales en Skype Empresarial Server
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
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Resumen: obtenga información sobre el informe de errores principales en Skype Empresarial Server.'
ms.openlocfilehash: bd03dc921e8df122f4e1ac3ca5cf15195a84b13e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816690"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Informe de errores principales en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de errores principales en Skype Empresarial Server.
  
El Informe de errores principales proporciona una presentación de los errores más frecuentes y las tendencias en el tiempo. Los errores se basan en una combinación de las dos métricas siguientes:
  
- **Id. de diagnóstico**. Identificador único (en forma de un encabezado de ms-diagnostics) que se adjunta a un mensaje SIP. Los Id. de diagnóstico proporcionan información útil para la solución de problemas relacionados con la llamada.
    
- **Código de respuesta**. Los códigos de respuesta se usan en las sesiones de comunicación SIP para responder a solicitudes SIP. Por ejemplo, supongamos que Ken envía la solicitud INVITE a Pilar Ackerman (es decir, supongamos que Ken Myer llama Pilar Ackerman). Si Pilar responde, su teléfono le enviará el código de respuesta 200 (OK), indicando al teléfono de Ken que Pilar ha respondido. El informe de errores principales solo incluye los códigos de respuesta que se enviaron en respuesta a un error de llamada; Skype Empresarial Server no realiza un seguimiento de todos los códigos de respuesta emitidos durante el curso de una llamada.
    
No solo se proporciona información del número total de sesiones donde se produjo un error, sino también del número total de usuarios a los que afectó el error.
  
## <a name="accessing-the-top-failures-report"></a>Acceso al Informe de errores principales

Desde la página Informes supervisión se obtiene acceso al Informe de errores principales. Al hacer clic en la métrica Sesiones notificadas se le llevará al informe de distribución [de errores en Skype Empresarial Server.](failure-distribution-report.md)
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Hacer el mejor uso del Informe de errores principales

El Informe de errores principales es inusual en un sentido: le permite filtrar a la vez hasta 5 Id. de diagnóstico. (Normalmente, solo se puede filtrar por un elemento , como una dirección SIP de usuario, a la vez). Para filtrar por varios identificadores de diagnóstico, simplemente escriba cada identificador en el cuadro Id. de diagnóstico, separando los identificadores mediante comas. (Si lo desea, puede dejar un espacio en blanco después de cada coma). Por ejemplo:
  
1011, 2412, 1033, 52116, 1008
  
Haga eso y solo aparecerán las llamadas erróneas que notificaron al menos uno de esos cinco Id. de diagnóstico.
  
Si coloca el mouse sobre un código de respuesta verá una información sobre herramientas que le indica el significado del código de respuesta en cuestión. Por ejemplo, si coloca el mouse sobre el código de respuesta 486 verá este mensaje:
  
No disponible aquí.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de errores más comunes le permite filtrar los datos en función de aspectos tales como el tipo de actividad (sesión punto a punto o sesión de conferencia) o por el código de respuesta SIP que acompañó a la sesión fallida. Es posible también elegir la forma en la que los datos deben agruparse. En este caso, los usos se agrupan por hora, día, semana o mes.
  
La siguiente tabla muestra los filtros que puede utilizar con el informe de errores más comunes.
  
**Filtros del informe de errores más comunes**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Tipo de actividad** <br/> | Tipo de actividad. Seleccione una de las siguientes opciones: <br/>  [Todos] <br/>  Punto a punto <br/>  Conferencia <br/> |
|**Modalidad** <br/> |En este momento, la única opción disponible es **[Todas]**.  <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Categoría** <br/> | Tipo de error. Seleccione una de las siguientes opciones: <br/>  Error esperado e inesperado <br/>  Error inesperado <br/>  Un "error esperado" es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen. Un "error inesperado" es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, tal cosa se identificaría como un error inesperado. <br/> |
|**Código de respuesta** <br/> |Código de respuesta SIP enviado cuando la conferencia ha fallado. Escriba el código de respuesta en su totalidad, como por ejemplo:  <br/> 400  <br/> |
|**Id. de diagnóstico** <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de errores más comunes.
  
**Métricas del informe de errores más comunes**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Rank** <br/> |Sí  <br/> |Clasificación relativa basada en el número de sesiones de las que se informa.  <br/> |
|**Sesiones de las que se informa** <br/> |Sí  <br/> |Número total de sesiones con error basadas en el Id. de diagnóstico y en el código de respuesta SIP.  <br/> |
|**Usuarios afectados** <br/> |Sí  <br/> |Número total de usuarios afectados por la sesión con error.  <br/> |
|**Información del error** <br/> |No  <br/> |Información detallada sobre el error, incluido el Id. de diagnóstico, el código de respuesta SIP y la descripción de los motivos por los que se produjo un error en la sesión.  <br/> |
|**Tendencia en el pasado** <br/> |No  <br/> |Gráfico de sesiones con error a lo largo del tiempo.  <br/> |
   

