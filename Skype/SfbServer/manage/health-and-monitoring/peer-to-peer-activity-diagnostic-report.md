---
title: Informe de diagnóstico de actividad punto a punto en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Resumen: Información sobre el informe de diagnóstico de actividad punto a punto en Skype para Business Server.'
ms.openlocfilehash: ccc0c793a27df51c86d7ae0a6a9b575c7f6a5659
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20980819"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Informe de diagnóstico de actividad punto a punto en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de diagnóstico de actividad punto a punto en Skype para Business Server.
  
El informe de diagnósticos de actividad punto a punto proporciona información sobre el éxito y error de sus sesiones de comunicación punto a punto. Tenga en cuenta que Skype para Business Server distingue entre distintos tipos de error:
  
- **Error esperado**. Un error esperado es normalmente un error solo en el sentido más técnico. Por ejemplo, supongamos que llama a alguien, pero que esta persona está fuera de la oficina y no puede responder al teléfono. Dado que no se respondió la llamada, esta se considera técnicamente un error. Por otro lado, era un error esperado: Skype para Business Server no esperan que responda a la llamada si no está disponible para responder al teléfono. De la misma manera, se producirá un error inesperado si intenta enviar un mensaje instantáneo a un usuario que se encuentra fuera de línea, o ha iniciado sesión, solo en un teléfono que no admite mensajería instantánea.
    
- **Error inesperado**. Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra. Por ejemplo, supongamos que se llama a persona a alguien y está disponible para atender la llamada; Sin embargo, cuando intente Skype para Business Server enrutar la llamada al correo de voz de la llamada se produce un error debido a que se ha perdido la conectividad con la mensajería unificada de Exchange. Ese es un error inesperado; esperaría que las llamadas siempre se pudieran enrutar al correo de voz. Como regla general, los errores inesperados son errores verdaderos: hay problemas que probablemente no se pueden remediar a través de la capacitación del usuario o medidas similares.
    
Tenga en cuenta que es posible que las métricas de éxito, errores esperados y errores inesperados no se sumen a la métrica de sesiones totales. Por ejemplo, en la ilustración anterior, tenemos los siguientes valores:
  
|**Correctas**|**Errores esperados**|**Errores inesperados**|**Total de sesiones**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Si suma 2024 + 469 + 16, obtiene un total de 2.509 sesiones, aunque la columna Total de sesiones muestra un total de 2.521 sesiones. Las 12 sesiones "que faltan" son sesiones que el sistema no puede clasificar como correctas o no correctas. En ocasiones, que será el caso cuando un producto de terceros presenta un nuevo código de diagnóstico que no esté familiarizado para Skype para Business Server. Cuando eso sucede, las llamadas realizadas usando ese producto, y la notificación de ese código de diagnóstico, no siempre se pueden clasificar como correcto, un error esperado o un error inesperado.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Obtener acceso al informe de diagnósticos de actividad punto a punto

Al informe de diagnósticos de actividad punto a punto se obtiene acceso desde la página principal de informes de supervisión. Puede acceder al [Informe de distribución de errores en Skype para Business Server](failure-distribution-report.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Volumen de errores inesperados
    
- Volumen de errores esperados
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Haciendo el mejor uso del informe de diagnósticos de actividad punto a punto

Hay varias maneras para poder filtrar el informe de diagnósticos de actividad punto a punto pero, de manera predeterminada, dichas opciones de filtrado están ocultas para su visión. Para ver las opciones de filtrado disponibles para usted, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior derecha de la ventana de informe. Cuando lo haga, las opciones de filtrado estarán disponibles para su uso.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de diagnóstico de actividad punto a punto permite filtrar por la modalidad de sesión (por ejemplo, mensajería instantánea, transferencia de archivos o uso de aplicaciones compartidas). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de diagnóstico de actividad punto a punto.
  
**Filtros del informe de diagnóstico de actividad punto a punto**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Modalidad** <br/> | Indica el tipo de actividad de comunicación que tuvo lugar. Seleccione una de las opciones siguientes: <br/>  [Todas] <br/>  Mensajería instantánea <br/>  Transferencia de archivos <br/>  Uso compartido de aplicaciones <br/>  Audio <br/>  Vídeo <br/> |
   
## <a name="metrics-per-modality"></a>Métricas (por modalidad)

En la tabla siguiente, se muestra la información proporcionada en el informe de diagnóstico de actividad punto a punto para cada modalidad.
  
**Métricas (por modalidad)**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Volumen de corrección** <br/> |No  <br/> |Cantidad total de sesiones punto a punto correctas.  <br/> |
|**Porcentaje de corrección** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que se completaron con problemas importantes. Se calcula dividiendo el volumen de corrección por el total de sesiones.  <br/> |
|**Volumen de errores esperados** <br/> |No  <br/> |Cantidad total de sesiones en las que se produjo un "error esperado".  <br/> Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.  <br/> |
|**Porcentaje de errores esperados** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que experimentaron un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.  <br/> |
|**Volumen de errores inesperados** <br/> |No  <br/> |Cantidad total de sesiones en las que se produjo un "error inesperado".  <br/> Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.  <br/> |
|**Porcentaje de errores inesperados** <br/> |No  <br/> |Porcentaje de sesiones punto a punto que experimentaron un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.  <br/> |
|**Total de sesiones** <br/> |No  <br/> |Cantidad total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
   

