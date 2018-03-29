---
title: Informe de lista de llamadas de grupo de respuesta en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Resumen: Conozca la aplicación de grupo de respuesta en Skype para Business Server 2015.'
ms.openlocfilehash: b01ba945740216e38c37c35cbfc519d682916dda
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="response-group-call-list-report-in-skype-for-business-server-2015"></a>Informe de lista de llamadas de grupo de respuesta en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre la aplicación de grupo de respuesta en Skype para Business Server 2015.
  
La aplicación de grupo de respuesta proporciona una manera de Skype para Business Server 2015 contestar y enrutar llamadas basándose en el número que se ha marcado y, opcionalmente, en las respuestas del llamador a una serie de preguntas. Normalmente, las llamadas grupo de respuesta no se enrutan a una persona individual pero, en su lugar, se dirigen a un equipo de personas que se conoce como un grupo de agentes. Por ejemplo, si alguien llama el número de teléfono para el departamento de soporte, Skype para Business Server 2015 puede enrutar automáticamente que la llamada el primer agente de mesa de ayuda disponible. Alternativamente, Skype para Business Server podría pedir una serie de preguntas ("Presione 1 si tiene problemas de hardware. Pulse 2 si tiene problemas de software. Presione 3 si tiene problemas de red.") y, a continuación, enrutar la llamada al agente de asistencia al cliente ayuda más apropiado basándose en la respuesta a esas preguntas.
  
El Informe de lista de llamadas de grupo de respuesta representa una colección de llamadas que reúnen unas características especificadas (tipo de llamada, periodo de tiempo en que se hizo). El Informe de uso del grupo de respuesta (que necesita abrirse antes de abrir el Informe de lista de llamadas de grupo de respuesta) reconoce los siguientes tipos de llamada:
  
- **Llamadas recibidas**. Cantidad total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.
    
- **Llamadas correctas**. Cantidad total de llamadas respondidas por la aplicación Grupo de respuesta.
    
- **Llamadas ofrecidas**. Cantidad total de llamadas transferidas a un agente de Grupo de respuesta.
    
- **Llamadas contestadas**. Cantidad total de llamadas contestadas realmente por un agente de Grupo de respuesta.
    
- **Porcentaje de llamadas abandonadas.** Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, luego, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, necesita restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. Luego, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30 %.
    
- **Llamadas transferidas**. Cantidad total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.
    
## <a name="accessing-the-response-group-call-list-report"></a>Acceso al informe de lista de llamadas de grupo de respuesta

El informe de lista de grupo de respuesta llame sólo puede accederse haciendo clic en una de las siguientes métricas que se encuentra en el [Informe de uso de grupo de respuesta en Skype para Business Server 2015](response-group-usage-report.md):
  
- Llamadas recibidas
    
- Llamadas correctas
    
- Llamadas ofrecidas
    
- Llamadas contestadas
    
- Llamadas transferidas
    
## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Cómo sacar el máximo partido al Informe de lista de llamadas de grupo de respuesta

El Informe de lista de llamadas de grupo de respuesta le permite limitar los datos que se muestran en las llamadas en las que participa un flujo de trabajo de grupos de respuesta en particular. Para ello, tendrá que escribir el URI del flujo de trabajo (es decir, su dirección SIP) en el cuadro URI de flujo de trabajo. Ahora bien, para poder hacer eso, primero tendrá que poder ver el cuadro URI de flujo de trabajo. Para mostrar las opciones de filtrado del Informe de lista de llamadas de grupo de respuesta, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior izquierda de la ventana de informes.
  
Tenga en cuenta que, al pasar el mouse sobre Código de respuesta o Id. de diagnóstico, la lista de llamadas de grupo de respuesta no muestra información sobre ninguna de esas dos métricas. Si necesita más información, podría Observe el código de respuesta o el Id. de diagnóstico y, a continuación, busque los valores en el [Informe de errores principales Skype para Business Server 2015](top-failures-report.md).
  
Ante una pregunta como "¿Qué flujo de trabajo concreto recibió más llamadas?", puede hacer lo siguiente:
  
1. En el Informe de uso del grupo de respuesta, establezca el periodo de tiempo deseado y luego haga clic en la métrica Llamadas recibidas. Se abrirá el Informe de lista de llamadas de grupo de respuesta.
    
2. Exporte los datos que se muestran en el Informe de lista de llamadas de grupo de respuesta. Por ejemplo, puede exportar los datos en formato Microsoft Excel y luego usar Excel para convertir los datos a un archivo de valores separados por comas.
    
3. Ejecute sus análisis con Windows PowerShell.
    
Por ejemplo, si ha guardado los datos en un archivo de nombre C:\Data\Response_Group_Call_List_Report.csv, puede utilizar el siguiente comando para obtener el número total de llamadas recibidas para cada flujo de trabajo que figure en el informe:
  
```
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

La información que se mostrará será similar a esta:
  
```
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
```

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de lista de llamadas de grupo de respuesta.
  
**Filtros de informe de lista de grupo de respuesta llamada**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**URI de flujo de trabajo** <br/> |Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:  <br/> SIP:Helpdesk@litwareinc.com  <br/> |
|**Llamadas** <br/> | Puede seleccionar entre los siguientes tipos de llamada: <br/>  Llamadas recibidas <br/>  Llamadas correctas <br/>  Llamadas ofrecidas <br/>  Llamadas contestadas <br/>  Llamadas transferidas <br/> |
   
## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información que facilita el informe de lista de llamadas de grupo de respuesta para cada llamada recibida por la aplicación Grupo de respuesta.
  
**Métricas de informe de lista de grupo de respuesta llamada**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Autor de llamada** <br/> |No  <br/> |Dirección SIP del autor de la llamada.  <br/> |
|**Flujo de trabajo** <br/> |No  <br/> |Dirección SIP del flujo de trabajo de Grupo de respuesta.  <br/> |
|**Hora de inicio** <br/> |No  <br/> |Fecha y hora en que se inició la llamada.  <br/> |
|**Hora de finalización** <br/> |No  <br/> |Fecha y hora en que finalizó la llamada.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
   

