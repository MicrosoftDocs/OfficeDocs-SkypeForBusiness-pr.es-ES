---
title: Informe de diagnóstico de actividad punto a punto en Skype Empresarial Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Resumen: obtenga información sobre el informe de diagnósticos de actividad punto a punto en Skype Empresarial Server.'
ms.openlocfilehash: 1988dbbc6cf1e2bc54eeafee95756e7633d0ffde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827740"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico de actividad punto a punto en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico de actividad punto a punto en Skype Empresarial Server.
  
El informe de diagnósticos de actividad punto a punto proporciona información acerca del éxito y error de sus sesiones de comunicación punto a punto. Tenga en cuenta que Skype Empresarial Server distingue entre diferentes tipos de error:
  
- **Error esperado**. Un error esperado es normalmente un error solo en el sentido más técnico. Por ejemplo, supongamos que llama a alguien, pero que esta persona está fuera de la oficina y no puede responder al teléfono. Dado que no se respondió la llamada, esta se considera técnicamente un error. Por otro lado, este fue un error esperado: Skype Empresarial Server no espera que responda al teléfono si no está disponible para responder al teléfono. De la misma manera, se producirá un error inesperado si intenta enviar un mensaje instantáneo a un usuario que se encuentra fuera de línea, o ha iniciado sesión, solo en un teléfono que no admite mensajería instantánea.
    
- **Error inesperado**. Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra. Por ejemplo, supongamos que llama a alguien y esa persona está disponible para responder a la llamada; sin embargo, cuando Skype Empresarial Server intenta enrutar la llamada al correo de voz, se produce un error porque se ha perdido la conectividad a la mensajería unificada de Exchange. Se trata de un error inesperado: se espera que las llamadas siempre se puedan enrutar al correo de voz. Como regla general, los errores inesperados son errores verdaderos: hay problemas que probablemente no se pueden remediar a través de la capacitación del usuario o medidas similares.
    
Tenga en cuenta que es posible que las métricas de éxito, errores esperados y errores inesperados no se sumen a la métrica de sesiones totales. Por ejemplo, en la ilustración anterior, tenemos los siguientes valores:
  
|**Operaciones correctas.**|**Errores esperados**|**Errores inesperados**|**Total de sesiones**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16   <br/> |2521  <br/> |
   
Si suma 2024 + 469 + 16, obtiene un total de 2.509 sesiones, aunque la columna Total de sesiones muestra un total de 2.521 sesiones. Las 12 sesiones "que faltan" son sesiones que el sistema no puede clasificar como correctas o no correctas. A veces, esto ocurre cuando un producto de terceros introduce un nuevo código de diagnóstico que no está familiarizado con Skype Empresarial Server. Cuando eso sucede, las llamadas realizadas usando ese producto, y la notificación de ese código de diagnóstico, no siempre se pueden clasificar como correcto, un error esperado o un error inesperado.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Obtener acceso al informe de diagnósticos de actividad punto a punto

Al informe de diagnósticos de actividad punto a punto se obtiene acceso desde la página principal de informes de supervisión. Puede obtener acceso al informe [de distribución de errores en Skype Empresarial Server](failure-distribution-report.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Volumen de errores inesperados
    
- Volumen de errores esperados
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Haciendo el mejor uso del informe de diagnósticos de actividad punto a punto

Hay varias maneras para poder filtrar el informe de diagnósticos de actividad punto a punto pero, de manera predeterminada, dichas opciones de filtrado está ocultas para su visión. Para ver las opciones de filtrado disponibles para usted, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior derecha de la ventana de informe. Una vez haga eso, las opciones de filtrado estarán disponibles para su uso.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de diagnóstico de actividad punto a punto permite filtrar por la modalidad de sesión (por ejemplo, mensajería instantánea, transferencia de archivos o uso de aplicaciones compartidas). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de diagnóstico de actividad punto a punto.
  
**Filtros del informe de diagnóstico de actividad punto a punto**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Modalidad** <br/> | Indica el tipo de actividad de comunicación que tuvo lugar. Seleccione una de las opciones siguientes: <br/>  [Todos] <br/>  Mensajería instantánea <br/>  Transferencia de archivos <br/>  Uso compartido de aplicaciones <br/>  Audio <br/>  Vídeo <br/> |
   
## <a name="metrics-per-modality"></a>Métricas (por modalidad)

En la tabla siguiente, se muestra la información proporcionada en el informe de diagnóstico de actividad punto a punto para cada modalidad.
  
**Métricas (por modalidad)**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de corrección** <br/> |No  <br/> |Número total de sesiones punto a punto correctas.  <br/> |
|**Porcentaje de corrección** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que se completaron con problemas importantes. Se calcula dividiendo el volumen de corrección por el total de sesiones.  <br/> |
|**Volumen de errores esperados** <br/> |No  <br/> |Número total de sesiones en las que se produjo un "error esperado".  <br/> Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.  <br/> |
|**Porcentaje de errores esperados** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que experimentaron un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.  <br/> |
|**Volumen de errores inesperados** <br/> |No  <br/> |Número total de sesiones en las que se produjo un "error inesperado".  <br/> Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.  <br/> |
|**Porcentaje de errores inesperados** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que experimentaron un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.  <br/> |
|**Total de sesiones** <br/> |No  <br/> |Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
   

