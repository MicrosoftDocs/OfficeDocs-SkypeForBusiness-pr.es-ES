---
title: Informe de dispositivos en Skype Empresarial Server
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
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Resumen: obtenga información sobre el informe de dispositivos en Skype Empresarial Server.'
ms.openlocfilehash: 6fd03c402209f5ab33db91038406ac0a5b930ba9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767728"
---
# <a name="device-report-in-skype-for-business-server"></a>Informe de dispositivos en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de dispositivos en Skype Empresarial Server.
  
Es posible que el informe de dispositivos se titulara mejor como informe de micrófono y altavoces; esto se debe a que el informe de dispositivos recupera métricas relacionadas con llamadas (como porcentaje de llamadas deficientes, eco y tiempo de cambio de voz) agrupadas por los micrófonos y altavoces usados en la llamada. Si está interesado en los teléfonos IP (también denominados comúnmente "dispositivos"), use el informe de inventario de ip Teléfono en Skype Empresarial Server en su [lugar.](ip-phone-inventory-report.md)
  
El informe de dispositivos es extremadamente útil para los administradores a la hora de determinar si un tipo específico de dispositivo está experimentando grandes volúmenes de llamadas de mala calidad que otros. A su vez, esto podría influir en cualquier decisión que deba tomar cuando llegue el momento de comprar nuevos dispositivos o reemplazar los dispositivos existentes.
  
De forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces/auriculares (el dispositivo de representación) usados en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación: de forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces/auriculares (el dispositivo de representación) usados en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación:
  
- Dispositivo de captura: micrófono (Audio HD digital integrado SoundMAX)
    
- Dispositivo render: auriculares auriculares (Microsoft LifeChat LX-3000)
    
Si esos usuarios realizaron un total de 254 llamadas, verá una entrada como esta en el informe:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares auriculares (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Ahora, supongamos que tienes un número de usuarios que usan ese mismo dispositivo de captura, pero un dispositivo de representación diferente. En ese caso, tendrás una segunda entrada de línea en el informe, una para esa combinación única de dispositivo de captura y dispositivo de representación:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares auriculares (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Altavoces (Audio HD digital integrado SoundMAX)  <br/> |319  <br/> |
   
Si prefieres ver totales combinados para un dispositivo determinado (por ejemplo, para el dispositivo de captura SoundMAX, independientemente del dispositivo de representación usado), selecciona la opción adecuada en la lista desplegable Tipo de dispositivo (dispositivo de captura o Dispositivo render). Si seleccionas Capturar dispositivo en este ejemplo, esto te dará una salida similar a la siguiente:
  
|**Dispositivo de captura**|**Volumen de llamadas**|
|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Acceso al informe de dispositivos

Normalmente, se tiene acceso al informe de dispositivos desde la página principal de informes de supervisión. Sin embargo, si estás viendo el Informe de detalles de llamadas en [Skype Empresarial Server](call-detail-report.md) puedes explorar en profundidad el Informe de dispositivos para un dispositivo específico haciendo clic en cualquiera de las siguientes métricas:
  
- Dispositivo de captura
    
- Representar dispositivo
    
Desde el Informe de dispositivos, puede explorar en profundidad el informe de lista de [llamadas en Skype Empresarial Server](call-list-report-0.md) haciendo clic en cualquiera de las siguientes métricas:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
## <a name="making-the-best-use-of-the-device-report"></a>Hacer el mejor uso del informe de dispositivos

Cuando se trata de nombres de dispositivos, el informe de dispositivos es extremadamente detallado; por ejemplo, supongamos que tiene los siguientes dispositivos de captura:
  
- Micrófono Aastra 3002 (2- Aastra 3002)
    
- Micrófono Aastra 3002 (3- Aastra 3002)
    
- Micrófono Aastra 3002 (Aastra 3002)
    
- Aastra 6725ip
    
- Micrófono Aastra 6725ip (10- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (10- Aastra 6725ip)-V0
    
- Micrófono Aastra 6725ip (2- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (3- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (4- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (5- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (6- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (7- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (9- Aastra 6725ip)
    
- Micrófono Aastra 6725ip (9- Aastra 6725ip)-V0
    
- Micrófono Aastra 6725ip (Aastra 6725ip)
    
- Micrófono Aastra 6725ip (Aastra 6725ip)-V0
    
- Micrófono Aastra 6725ip (dispositivo de audio USB)
    
- Micrófono Aastra 6725ip (dispositivo de audio USB)-V0
    
> [!NOTE]
> Ten en cuenta que es posible que los nombres de dispositivos de captura no sean los mismos si estás ejecutando versiones localizadas de Skype Empresarial Server. Un dispositivo denominado Micrófono Aastra 6725ip (Aastra 6725ip)-V0 en inglés de Estados Unidos podría tener un nombre diferente en francés o español. 
  
A menudo, querrás ese nivel de detalle; en otras ocasiones, sin embargo, es posible que solo te interese cuántas llamadas usan cualquier micrófono de Aastra, independientemente del número de modelo. Una forma de obtener información como esta es exportar los datos del informe de dispositivo a Microsoft Excel y, a continuación, guardar esos datos en un archivo de valores separados por comas (por ejemplo, C:\Data\Devices_Report.csv). A continuación, puedes usar un conjunto de comandos similares a estos para importar el archivo .CSV en Windows PowerShell e informar del número total de llamadas realizadas con un dispositivo de captura de Aastra:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Esto devolverá un valor único que representa el número total de llamadas realizadas con un dispositivo de captura de Aastra. Por ejemplo: 384

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de dispositivos permite filtrar por elementos como el tipo de llamada (es decir, la llamada a una llamada de cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC). También se puede elegir cómo agrupar los datos. En este caso, los dispositivos se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se enumeran los filtros que puedes usar con el informe de dispositivos.
  
**Filtros de informes de dispositivos**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Causa del cambio de voz** <br/> |Motivo por el que una llamada debía colocarse en modo semidúplex para evitar el eco. En el modo semidúplex, la comunicación solo puede desplazarse en una dirección a la vez, de forma similar a la manera en que los usuarios se turnan al comunicarse con un walkie-talkie. Seleccione una de las siguientes opciones:  <br/> [All] None Bad timestamp Echo DNLP (dynamic nonlinear processor) Low complexity Bad device state Post-AEC echo (acoustic echo cancellation) |
|**Causa de eco** <br/> |Motivo por el que se detectó eco por encima del nivel aceptado en una llamada. (En telecomunicaciones, el eco es un reflejo del sonido, el mismo fenómeno que oirá si se oye al final de un pozo). Seleccione una de las siguientes opciones:  <br/> [All] None Bad timestamp Post-AEC echo (acoustic echo cancellation) ANLP (adaptive nonlinear processor) DNLP (dynamic nonlinear processor) Microphone clipping |
|**Tipo de llamada** <br/> |Indica el tipo de llamada que se realizó. Seleccione una de las siguientes opciones:  <br/> [All] Llamada de cliente Llamada RTC Llamada conferencia |
|**Tipo de acceso** <br/> |Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] Externo interno |
|**Tipo de red** <br/> |Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] Cable inalámbrico |
|**VPN** <br/> |Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] VPN no VPN |
|**Tipo de dispositivo** <br/> |Indica el tipo de dispositivo. Seleccione una de las siguientes opciones:  <br/> Capture device Render device Capture/Render device pair |
|**Nombre de dispositivo** <br/> |Nombre del dispositivo de captura o representación. Puedes escribir el nombre completo del dispositivo o cualquier parte del nombre del dispositivo. Por ejemplo, para buscar el micrófono del dispositivo (Microsoft LifeCam VX-1000)., puedes escribir el nombre completo del dispositivo de la siguiente manera:  <br/> Micrófono (Microsoft LifeCam VX-1000).  <br/> O bien, puede escribir solo una parte del nombre. Por ejemplo:  <br/> LifeCam  <br/> Tenga en cuenta que el filtro anterior devuelve cualquier dispositivo que contenga la cadena "LifeCam" en cualquier lugar de su nombre.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el Informe de dispositivos.
  
**Métricas de informe de dispositivos**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Dispositivo de captura** <br/> |Sí  <br/> |Dispositivo (por ejemplo, un micrófono o cámara web) usado para transmitir audio.  <br/> |
|**Dispositivo de presentación** <br/> |Sí  <br/> |Dispositivo (por ejemplo, auriculares o altavoces) usado para recibir audio.  <br/> |
|**Volumen de llamadas** <br/> |Sí  <br/> |Número total de llamadas realizadas.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |Sí  <br/> |Porcentaje de llamadas que se clasificaron como "deficientes". Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).  <br/> |
|**Usuarios únicos** <br/> |Sí  <br/> |Usuarios únicos que usaron el dispositivo. Si un usuario usaba el dispositivo 13 veces, contaría como un usuario único, lo mismo que un usuario que solo usaba el dispositivo una sola vez.  <br/> |
|**Relación de tiempo de cambio de voz** <br/> |Sí  <br/> |Porcentaje de la llamada que tuvo que realizarse en modo semidúplex para evitar el eco. En el modo semidúplex, la comunicación solo puede desplazarse en una dirección a la vez, de forma similar a la manera en que los usuarios se turnan al comunicarse con un walkie-talkie.  <br/> |
|**Relación de micrófono que no funciona** <br/> |Sí  <br/> |Porcentaje de la llamada en la que el dispositivo de captura no funcionaba en un nivel aceptable. Un alto valor sugiere que los problemas de calidad con la llamada se deba principalmente a que el dispositivo de captura no funcionaba como se esperaba.  <br/> |
|**Relación de altavoz que no funciona** <br/> |Sí  <br/> |Porcentaje de la llamada en la que el dispositivo de representación no funcionaba en un nivel aceptable. Un alto valor sugiere que los problemas de calidad con la llamada se deba principalmente a que el dispositivo de representación no funcionaba como se esperaba.  <br/> |
|**Llamadas con conmutador de voz (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas que se tuvieron que colocar en modo semidúplex. En el modo semidúplex, la comunicación solo puede desplazarse en una dirección a la vez, de forma similar a la manera en que los usuarios se turnan al comunicarse con un walkie-talkie.  <br/> |
|**Micrófono eco en (%)** <br/> |Sí  <br/> |Porcentaje de tiempo en el que se detectó eco en la secuencia de captura de micrófono. Por lo general, los valores son bajos para auriculares o auriculares, y superiores para teléfonos de altavoces o altavoces independientes. En el caso de los dispositivos que admiten la cancelación de eco acústico abordo, los valores altos indican una pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.  <br/> |
|**Envío de eco (%)** <br/> |Sí  <br/> |Porcentaje de eco transmitido a otros usuarios.  <br/> |
|**Llamadas con eco (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas que tenían eco que superó el nivel aceptable.  <br/> |
   

