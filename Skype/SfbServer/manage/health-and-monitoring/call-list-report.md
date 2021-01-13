---
title: Informe de lista de llamadas de grupo de respuesta en Skype Empresarial Server
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
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Resumen: obtenga información sobre la aplicación Grupo de respuesta en Skype Empresarial Server.'
ms.openlocfilehash: 416a0e7b7a7aebaeae84a00c04a7ab5c4e1a5bf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826500"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Informe de lista de llamadas de grupo de respuesta en Skype Empresarial Server

**Resumen:** Obtenga información sobre la aplicación Grupo de respuesta en Skype Empresarial Server.

La aplicación Grupo de respuesta permite a Skype Empresarial Server responder y enrutar llamadas telefónicas en función del número marcado y, opcionalmente, de las respuestas del autor de la llamada a una serie de preguntas. Normalmente, las llamadas de grupo de respuesta no se enrutar a una persona individual, sino que, en su lugar, se enrutar a un equipo de personas a las que se hace referencia como un grupo de agentes. Por ejemplo, si alguien llama al número de teléfono de su servicio de ayuda, Skype Empresarial Server puede enrutar automáticamente esa llamada al primer agente de servicio de ayuda disponible. Como alternativa, Skype Empresarial Server podría hacer una serie de preguntas ("Pulse 1 si tiene problemas de hardware. Presione 2 si tiene problemas de software. Presione 3 si tiene problemas de red. y, a continuación, enruta la llamada al agente de servicio de ayuda más adecuado en función de la respuesta a esas preguntas.

El informe de lista de llamadas de grupo de respuesta representa una colección de llamadas realizadas durante un período de tiempo especificado y para un tipo de llamada especificado. El informe de uso del grupo de respuesta (que debe abrirse primero para poder abrir el informe de lista de llamadas de grupo de respuesta) reconoce los siguientes tipos de llamada:

- **Llamadas recibidas**. Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.

- **Llamadas correctas**. Número total de llamadas que la aplicación Grupo de respuesta ha seleccionado.

- **Llamadas ofrecidas**. Número total de llamadas transferidas a un agente de Grupo de respuesta.

- **Llamadas contestadas**. Número total de llamadas contestadas realmente por un agente de Grupo de respuesta.

- **Porcentaje de llamadas abandonadas.** Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, debe restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.

- **Llamadas transferidas**. Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.

## <a name="accessing-the-response-group-call-list-report"></a>Acceso al informe de lista de llamadas de grupo de respuesta

Solo se puede obtener acceso al informe de lista de llamadas de grupo de respuesta haciendo clic en una de las siguientes métricas que se encuentran en el informe de uso del grupo de respuesta [en Skype Empresarial Server:](response-group-usage-report.md)

- Llamadas recibidas

- Llamadas correctas

- Llamadas ofrecidas

- Llamadas contestadas

- Llamadas transferidas

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Aprovechar al máximo el informe de lista de llamadas de grupo de respuesta

El informe de lista de llamadas de grupo de respuesta permite limitar los datos mostrados a las llamadas que implican un flujo de trabajo de grupo de respuesta determinado. Para ello, debe escribir el URI del flujo de trabajo (la dirección SIP del flujo de trabajo) en el cuadro URI de flujo de trabajo. Sin embargo, antes de poder hacerlo, debe poder ver el cuadro URI de flujo de trabajo. Para mostrar las opciones de filtrado para el informe de lista de llamadas de grupo de respuesta, haga clic en el botón Mostrar u ocultar parámetros en la parte superior izquierda de la ventana del informe.

Tenga en cuenta que la lista de llamadas de grupo de respuesta no muestra información sobre el código de respuesta o el id. de diagnóstico si mantiene el mouse sobre cualquiera de esas métricas. Si necesita más información, puede tener en cuenta el código de respuesta o el id. de diagnóstico y, a continuación, buscar esos valores en el informe de errores principales en [Skype Empresarial Server.](top-failures-report.md)

Una pregunta como esta: "¿Qué flujo de trabajo individual recibió más llamadas?", puede hacer lo siguiente:

1. En el Informe de uso del grupo de respuesta, establezca el período de tiempo deseado y, a continuación, haga clic en la métrica Llamadas recibidas. Se abrirá el informe de lista de llamadas de grupo de respuesta.

2. Exporte los datos que se muestran en el informe de lista de llamadas de grupo de respuesta. Por ejemplo, puede exportar los datos en formato Microsoft Excel y, a continuación, usar Excel para convertir esos datos en un archivo de valores separados por comas.

3. Ejecute los análisis con Windows PowerShell.

Por ejemplo, si ha guardado los datos en un archivo denominado C:\Data\Response_Group_Call_List_Report.csv, puede usar el siguiente comando para devolver el número total de llamadas recibidas para cada flujo de trabajo enumerado en el informe:

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

Esa información será similar a la siguiente:

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente se enumeran los filtros que puede usar con el informe de lista de llamadas de grupo de respuesta.

**Filtros del informe de lista de llamadas de grupo de respuesta**


| **Nombre**               | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
| **Para** <br/>           | Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/>        |
| **URI de flujo de trabajo** <br/> | Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Llamadas** <br/>        | Puede seleccionar uno de los siguientes tipos de llamada: <br/>  Llamadas recibidas <br/>  Llamadas correctas <br/>  Llamadas ofrecidas <br/>  Llamadas contestadas <br/>  Llamadas transferidas <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de lista de llamadas de grupo de respuesta para cada llamada recibida por la aplicación Grupo de respuesta.

**Métricas del informe de lista de llamadas de grupo de respuesta**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Caller** <br/> |No  <br/> |Dirección SIP del autor de la llamada.  <br/> |
|**Flujo de trabajo** <br/> |No  <br/> |Dirección SIP del flujo de trabajo grupo de respuesta.  <br/> |
|**Hora de comienzo** <br/> |No  <br/> |Fecha y hora en que se inició la llamada.  <br/> |
|**Hora de finalización** <br/> |No  <br/> |Fecha y hora en que finalizó la llamada.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la sesión.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |


