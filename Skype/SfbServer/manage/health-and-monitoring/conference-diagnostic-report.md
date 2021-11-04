---
title: Informe de diagnóstico de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Resumen: obtenga información sobre el Informe de diagnóstico de conferencia usado en Skype Empresarial Server.'
ms.openlocfilehash: c62a45c6bff7a91e6d0252ecc1a8010e5098f42b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773590"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico de conferencia usado en Skype Empresarial Server.
  
El Informe de diagnósticos de conferencia facilita información sobre las sesiones de conferencia que se han completado correctamente y las que han presentado algún error. Tenga en cuenta Skype Empresarial Server distingue entre diferentes tipos de error:
  
- **Error esperado**. Un error esperado es, generalmente, un error en el sentido más técnico. Por ejemplo, supongamos que alguien inicia una conferencia, pero la comunicación se cuelga antes de que otros usuarios puedan unirse a ella. Técnicamente, eso es un error: la conferencia se ha iniciado, pero no se ha completado. Sin embargo, es un error que cabe esperar que ocurra, porque si el organizador cancela la conferencia antes de que otros usuarios se unan a ella, no podemos esperar que la conferencia se complete.
    
- **Error inesperado**. Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra. Por ejemplo, una conferencia que no se puede llevar a cabo porque no se ha podido recuperar la directiva de reunión del organizador. Ese es un error inesperado ya que siempre se deberían poder recuperar las directivas de reunión de un usuario.
    
Observe que las métricas Correcta, Error esperado y Error inesperado podrían no incluirse en la métrica Total de sesiones. Por ejemplo, podría ver los siguientes valores en el informe:
  
|**Operaciones correctas.**|**Errores esperados**|**Errores inesperados**|**Total de sesiones**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Si sumamos 2024 + 469 + 16, obtenemos un total de 2.509 sesiones y, sin embargo, la columna Total de sesiones muestra 2.521 sesiones. Las 12 sesiones "que faltan" son las sesiones que el sistema no ha podido clasificar como de correcta ni de error. Esto a veces ocurre cuando un producto de terceros introduce un nuevo código de diagnóstico que no está familiarizado con el servidor de supervisión. Cuando esto ocurre, las llamadas realizadas mediante este producto que ocasionen ese código de diagnóstico no siempre se clasificarán como Correcta, Error esperado o Error inesperado.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Acceso al Informe de diagnósticos de conferencia

Al Informe de diagnósticos de conferencia, se accede desde la página de inicio de Informes de supervisión. Puede obtener acceso al informe de distribución de [errores en Skype Empresarial Server](failure-distribution-report.md) haciendo clic en cualquiera de las siguientes métricas:
  
- Volumen de errores inesperados
    
- Volumen de errores esperados
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Cómo hacer el mejor uso del Informe de diagnósticos de conferencia

El Informe de diagnósticos de conferencia incluye una serie de gráficos. Cada una de las columnas mostradas en el gráfico es, en realidad, un hipervínculo. Si hace clic en una columna, profundizará en el Informe de distribución de errores [en Skype Empresarial Server](failure-distribution-report.md) para ese período de tiempo y ese tipo de conferencia.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de diagnósticos de conferencia le permite filtrar elementos tales como el tipo de conferencia que se realiza (por ejemplo, una conferencia basada en un tema) o por el servidor perimetral que se usa en la conferencia. También puede elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de diagnósticos de conferencia
  
**Filtros del Informe de diagnósticos de conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2015, los datos se muestran para los días 8/7/2015 de 12:00 a 9/7/2015 12:00 AM (es decir, un total de 31 días de valor de datos). <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Sesiones de conferencia** <br/> | Indica el tipo de sesión de conferencia. Seleccione una de las siguientes opciones: <br/>  [All] <br/>  Sesiones de foco <br/>  Todas las sesiones de MCU <br/>  Conferencia de mensajería instantánea <br/>  Uso compartido de aplicaciones <br/>  Conferencia A/V <br/> |
   
## <a name="metrics"></a>Métricas

En la siguiente tabla se enumera la información proporcionada en el Informe de diagnósticos de conferencia para cada tipo de sesión de conferencia.
  
**Métricas del Informe de diagnósticos de conferencia**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de corrección** <br/> |No  <br/> |Número total de conferencias correctas  <br/> |
|**Porcentaje de corrección** <br/> |No  <br/> |Porcentaje de conferencias que se realizaron con problemas considerables. Se calcula dividiendo el volumen de sesiones correctas por el total de sesiones.  <br/> |
|**Volumen de errores esperados** <br/> |No  <br/> |Número total de conferencias donde ocurrió un "error esperado".  <br/> Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.  <br/> |
|**Porcentaje de errores esperados** <br/> |No  <br/> |Porcentaje de conferencias en las que se produjo un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.  <br/> |
|**Volumen de errores inesperados** <br/> |No  <br/> |Número total de conferencias donde ocurrió un "error inesperado".  <br/> Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.  <br/> |
|**Porcentaje de errores inesperados** <br/> |No  <br/> |Porcentaje de conferencias en las que se produjo un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.  <br/> |
|**Total de sesiones** <br/> |No  <br/> |Número total de conferencias, incluyendo conferencias correctas, conferencias con errores (tanto errores esperados como inesperados) y conferencias no categorizadas.  <br/> |
   

