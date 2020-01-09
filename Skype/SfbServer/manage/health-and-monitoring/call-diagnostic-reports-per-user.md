---
title: Informes de diagnósticos de llamadas (por usuario) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 'Resumen: Obtenga información sobre los informes de diagnóstico de llamadas por usuario que se usan en Skype empresarial Server.'
ms.openlocfilehash: c2ef55243680cbb8bc088c2b056b298428b70b50
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992075"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Informes de diagnósticos de llamadas (por usuario) en Skype empresarial Server
  
Los informes de diagnósticos de llamadas ofrecen información por usuario sobre sesiones de conferencia y de punto a punto con errores. En este momento, solo hay un informe, el **Informe de actividad del usuario**.

El Informe de actividad de usuario proporciona una lista detallada de sesiones de conferencia y de punto a punto realizadas por sus usuarios en un período determinado. A diferencia de muchos de los Informes de supervisión, el Informe de actividad de usuario une cada llamada a usuarios individuales. Por ejemplo, las sesiones de punto a punto especifican los URI del SIP de la persona que inició la llamada (el usuario De) y la persona a la que se realizó la llamada (el usuario Para). Si expande la información de una conferencia, verá una lista de todos los participantes de la conferencia y el rol que desempeñaban en esa conferencia.

Al Informe de actividad de usuario a veces se lo conoce como "informe de asistencia técnica" porque a menudo el personal de asistencia técnica lo utiliza para recuperar información de sesión para un usuario específico. Es posible establecer filtros para llamadas realizadas a o por un usuario particular con tan solo escribir el URI del SIP del usuario en el cuadro de prefijo de URI del usuario.

Si hace esto, el informe de actividad del usuario devolverá la información de cualquier usuario cuyo URI SIP empiece por la cadena especificada. Por ejemplo, si escribe **ken** en el cuadro URI, el Informe de actividad de usuario encontrará **Ken**.Myer@litwareinc.com. Pero, también encontrará a estos usuarios:

- **ken** AZI@litwareinc.com

- **ken** Burg@litwareinc.com

- **Ken**.Sanchez@litwareinc.com

- **Ken** Nedy@litwareinc.com

Para asegurarse de que se devuelva información únicamente para Ken Myer, escriba su URI completo (Ken.Myer@litwareinc.com) en el cuadro de búsqueda o, como mínimo, escriba el URI de Ken para distinguirlo de los demás usuarios de su organización. Por ejemplo:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Acceso al informe de actividad de usuario

Para obtener al Informe de actividad de usuario hay que ir a la página de inicio de Informes de supervisión. También puede comunicarse con el informe de actividad del usuario haciendo clic en la métrica de URI de usuario en el [Informe inventario de teléfonos IP de Skype empresarial Server](ip-phone-inventory-report.md). Desde el Informe de actividad de usuario, puede hacer clic en el URI de conferencia (para una conferencia) para obtener acceso al Informe de detalles de conferencia. De forma similar, al hacer clic en la métrica de detalle de una llamada de punto a punto, se le lleva al [informe detallado de sesión de punto a punto de Skype empresarial Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Hacer el mejor uso del informe de actividad de usuario

Aunque hay mucha información buena en el Informe de actividad de usuario, esa información puede a veces ser difícil de encontrar. Por ejemplo, toda la actividad de usuario que tiene lugar en la organización durante un período específico se incluye en el informe actividad de usuario. eso significa que, en el informe, la información sobre qué usuarios realmente usó Skype empresarial Server de alguna forma.

> [!NOTE]
> Técnicamente, es posible que algunas actividades de usuario no se registren: aunque Skype empresarial Server se esfuerza por mantener la información sobre todas las llamadas telefónicas, es posible que se haya realizado una llamada sin que la información sobre la llamada se escriba en el Database. Skype empresarial Server está diseñado para ofrecer un aspecto extremadamente preciso, pero no necesariamente perfecto, de la forma en que se usa Skype empresarial Server. (El hecho de que no haya garantía de que el 100% de todas las llamadas se grabe explica por qué no se debe usar la supervisión de Skype empresarial Server como sistema de facturación). En segundo lugar, un informe de supervisión solo puede mostrar, como máximo, 1.000 registros. Según la cantidad de actividad de usuario que tenga y el período de tiempo con el que trabaje, eso significa que su consulta podría no devolverle todos los datos realmente almacenados en la base de datos. 

- ¿Qué usuarios utilizaron en realidad el sistema durante este período?

- ¿Cuáles de mis usuarios fueron los más activos durante este período?

- ¿Los usuarios que realizan la mayor cantidad de llamadas telefónicas también son los usuarios que participan en la mayoría de las sesiones de mensajería instantánea?

Si necesita responder preguntas como estas, puede exportar los datos recuperados por los Informes de supervisión a una hoja de cálculos de Excel. Luego utiliza esa hoja de cálculos o un archivo de valores separados por comas para analizar los datos del modo en que no permite el Informe de actividad de usuario. Por ejemplo, imaginemos que ha exportado los datos del informe a Excel y luego a un archivo de valores separados por comas. En ese momento, puede importar los datos desde el. CSV a Windows PowerShell con un comando parecido a este:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Una vez importados los datos, puede usar comandos sencillos de Windows PowerShell para responder a sus preguntas. Por ejemplo, este comando devuelve una lista de usuarios únicos que han tenido el rol de "usuario De" en al menos una sesión:

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

Dicho de otra manera:

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Este comando enumera los usuarios únicos (en función de la cantidad total de sesiones en las que participaron):

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Eso devuelve datos similares a esto:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Este comando limita las sesiones informadas a aquellas que incluyeron audio como modalidad:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Si mantiene el cursor del mouse sobre cualquier identificador de diagnóstico mostrado en el informe, aparecerá una información sobre herramientas que describirá ese identificador.

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de actividad de usuario le permite filtrar los datos devueltos en función de aspectos tales como el tipo de actividad (es decir, sesiones punto a punto o sesiones de conferencia) o por la dirección SIP del usuario (permitiéndole ver las actividades de un usuario). Es posible también elegir la forma en la que tienen que agruparse los datos. En este caso, los usos se agrupan por hora, día, semana o mes.

La siguiente tabla muestra los filtros que puede utilizar con el informe de actividad de usuario.

**Filtros del informe de actividad de usuario**


| **Nombre.**   | **Descripción**  |
|:-----------|:--------|
| **De** <br/>             | Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/>                                                      |
| **Hasta** <br/>               | Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 17/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 17/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 13/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/>                                                             |
| **Tipo de actividad** <br/>    | Tipo de actividad. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Punto a punto <br/>  Una conferencia <br/>      |
| **Modalidad** <br/>         | La modalidad que tenga disponible dependerá de la opción seleccionada en Tipo de actividad. Si el tipo de actividad es de punto a punto, puede seleccionar mi; Transferencia de archivos; Uso compartido de aplicaciones; Facturación o vídeo como modalidad.  <br/> Si el Tipo de actividad es Conferencia, podrá seleccionar mensajería instantánea, conferencia telefónica; conferencia web; uso compartido de aplicaciones; conferencia de voz/vídeo o conferencia telefónica.  <br/>         |
| **Categoría de sesión** <br/> | Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Correcto <br/>  Error esperado <br/>  Error inesperado <br/>  Un "error esperado" es aquel que se espera que se produzca; por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que se produzca un error en cualquier llamada dirigida a dicho usuario. Un "error inesperado" es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no tendría que finalizar si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado. <br/> |
| **Prefijo de URI de usuario** <br/>  | Dirección SIP del usuario. Para ver únicamente registros del usuario Ken Myer necesita introducir la dirección SIP de Ken Myer. Por ejemplo:  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones punto a punto (es decir, sesiones con solo dos participantes).

**Métricas de las sesiones punto a punto**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Detalle** <br/> |No  <br/> |Al hacer clic en este elemento, el informe le muestra el informe de detalles de sesiones punto a punto correspondiente a la sesión seleccionada.  <br/> |
|**Remitente** <br/> |Sí  <br/> |Dirección SIP del usuario que inició la sesión punto a punto.  <br/> |
|**Destinatario** <br/> |Sí  <br/> |Dirección SIP del usuario que se unió a la sesión punto a punto.  <br/> |
|**Modalidades** <br/> |Sí  <br/> |Tipo de comunicación usado en la sesión. Por ejemplo, mensajería instantánea, sonido o transferencia de archivos.  <br/> |
|**Hora de invitación** <br/> |Sí  <br/> |Fecha y hora en las que se envió la invitación inicial a unirse a la sesión punto a punto.  <br/> |
|**Tiempo de respuesta** <br/> |Sí  <br/> |Fecha y hora en las que el destinatario aceptó la invitación a la sesión.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en las que finalizó la sesión punto a punto.  <br/> |
|**Id. de diagnóstico** <br/> |Sí  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones de conferencia (es decir, sesiones con tres o más participantes).

**Métricas de las sesiones de conferencia**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**URI de conferencia** <br/> |Sí  <br/> |Identificador único de la conferencia. Al hacer clic en este elemento, el informe le muestra el informe de detalles de conferencia de la sesión seleccionada. Al desplegar este elemento, el informe le muestra información sobre los participantes en la conferencia. Para más información, mire la sección "Métricas de los participantes en las conferencias" en este mismo tema.  <br/> |
|**Organizador** <br/> |Sí  <br/> |Dirección SIP del usuario que organizó la conferencia  <br/> |
|**Grupo de servidores** <br/> |Sí  <br/> |Nombre del servidor perimetral (si lo hay) usado en la conferencia.  <br/> |
|**Hora de inicio** <br/> |Sí  <br/> |Fecha y hora en las que comenzó la conferencia.  <br/> |
|**Hora de finalización** <br/> |Sí  <br/> |Fecha y hora en que la conferencia finalizó.  <br/> |

## <a name="metrics-for-conference-participants"></a>Métricas de los participantes en conferencias

En la tabla siguiente se muestra la información que recoge el informe de actividad de usuario sobre cada participante en una conferencia.

**Métricas de los participantes en conferencias**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Rol** <br/> |No  <br/> |Rol del usuario en la conferencia (por ejemplo, moderador).  <br/> |
|**Participante** <br/> |No  <br/> |Dirección SIP del usuario.  <br/> |
|**Conectividad** <br/> |No  <br/> |Tipo de conexión de red. Por ejemplo "Desde conexión interna" en el caso de las conexiones internas, o "Desde RTC" para usuarios que obtienen acceso por medio del marcado.  <br/> |
|**Hora de conexión** <br/> |No  <br/> |Fecha y hora en las que el usuario se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |No  <br/> |Fecha y hora en las que el usuario dejó la conferencia.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |

