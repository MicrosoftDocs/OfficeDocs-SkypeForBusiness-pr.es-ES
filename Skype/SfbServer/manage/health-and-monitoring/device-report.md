---
title: Informe de dispositivos en Skype Empresarial Server
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
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Resumen: obtenga información sobre el informe de dispositivos en Skype Empresarial Server.'
ms.openlocfilehash: 2471f232256e4715f271cd310f0b1415555ca4c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826420"
---
# <a name="device-report-in-skype-for-business-server"></a>Informe de dispositivos en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de dispositivos en Skype Empresarial Server.
  
El informe de dispositivos podría tener el título "Informe de micrófono y altavoces"; esto se debe a que el informe de dispositivos recupera métricas relacionadas con llamadas (como porcentaje de llamadas deficientes, eco y tiempo de conmutación de voz) agrupadas por los micrófonos y altavoces usados en la llamada. Si le interesan los teléfonos IP (también denominados "dispositivos"), use en su lugar el informe de inventario de teléfono IP en Skype Empresarial [Server.](ip-phone-inventory-report.md)
  
El informe de dispositivos es extremadamente útil para los administradores a la hora de determinar si un tipo específico de dispositivo está experimentando grandes volúmenes de llamadas de calidad deficiente que otros. A su vez, esto podría influir en cualquier decisión que deba tomar cuando llegue el momento de comprar nuevos dispositivos o reemplazar los dispositivos existentes.
  
De forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y auriculares (el dispositivo de representación) usados en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación: de forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y auriculares (el dispositivo de representación) usados en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación:
  
- Dispositivo de captura: micrófono (Audio HD digital integrado SoundMAX)
    
- Dispositivo de representación: auriculares con auriculares (Microsoft LifeChat RV-3000)
    
Si esos usuarios realizaron un total de 254 llamadas, verá una entrada como esta en el informe:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares para auriculares (Microsoft LifeChat RV-3000)  <br/> |254  <br/> |
   
Ahora, supongamos que tienes un número de usuarios que usan el mismo dispositivo de captura pero un dispositivo de representación diferente. En ese caso, tendrás una segunda entrada de línea en el informe, una para esa combinación única de dispositivo de captura y dispositivo de representación:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares para auriculares (Microsoft LifeChat RV-3000)  <br/> |254  <br/> |
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Altavoces (Audio HD digital integrado SoundMAX)  <br/> |319  <br/> |
   
Si prefieres ver los totales combinados de un dispositivo determinado (por ejemplo, para el dispositivo de captura SoundMAX, independientemente del dispositivo de representación usado), selecciona la opción adecuada en la lista desplegable Tipo de dispositivo (dispositivo de captura o dispositivo de representación). Si seleccionas el dispositivo de captura en este ejemplo, esto te dará una salida similar a la siguiente:
  
|**Dispositivo de captura**|**Volumen de llamadas**|
|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Acceso al informe de dispositivos

Normalmente se tiene acceso al informe de dispositivos desde la página principal de informes de supervisión. Sin embargo, si está viendo el informe de detalles de llamadas en Skype Empresarial [Server,](call-detail-report.md) puede explorar en profundidad el informe de dispositivos para un dispositivo específico haciendo clic en cualquiera de las métricas siguientes:
  
- Dispositivo de captura
    
- Dispositivo de representación
    
Desde el informe de dispositivos, puede explorar en profundidad el informe de lista de llamadas en [Skype Empresarial Server](call-list-report-0.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
## <a name="making-the-best-use-of-the-device-report"></a>Aprovechar al máximo el informe de dispositivos

En lo que respecta a los nombres de dispositivos, el informe de dispositivos es extremadamente detallado; por ejemplo, supongamos que tiene los siguientes dispositivos de captura:
  
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
> Tenga en cuenta que es posible que los nombres de los dispositivos de captura no sean los mismos si ejecuta versiones localizadas de Skype Empresarial Server. Un dispositivo denominado Micrófono Aastra 6725ip (Aastra 6725ip)-V0 en inglés de Estados Unidos podría tener un nombre diferente en francés o español. 
  
A menudo, querrás ese nivel de detalle; En otras ocasiones, sin embargo, es posible que solo le interese cuántas llamadas usan cualquier micrófono Aastra, independientemente del número de modelo. Una forma de obtener información como esta es exportar los datos del informe de dispositivos a Microsoft Excel y, a continuación, guardar esos datos en un archivo de valores separados por comas (por ejemplo, C:\Data\Devices_Report.csv). A continuación, puede usar un conjunto de comandos similares a estos para importar el archivo . Archivo CSV en Windows PowerShell y notificar el número total de llamadas realizadas con un dispositivo de captura Aastra:
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Esto devolverá un valor único que representa el número total de llamadas realizadas con un dispositivo de captura Aastra. Por ejemplo: 384

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de dispositivos le permite filtrar por aspectos como el tipo de llamada (es decir, la llamada de un cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC). También se puede elegir cómo agrupar los datos. En este caso, los dispositivos se agrupan por hora, día, semana o mes.
  
En la tabla siguiente se enumeran los filtros que puedes usar con el informe de dispositivos.
  
**Filtros del informe de dispositivos**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Causa del conmutador de voz** <br/> |Motivo por el que se tuvo que realizar una llamada en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación puede desplazarse en una sola dirección a la vez, de forma similar a la forma en que los usuarios toman turnos al comunicarse con un walkie-talkie. Seleccione una de las siguientes opciones:  <br/> [Todos] None Bad timestamp Echo DNLP (dynamic nonlinear processor) Low complexity Bad device state Post-AEC echo (de cancelación de ecos de ruido) |
|**Causa del eco** <br/> |Motivo por el que se detectó eco por encima del nivel aceptado en una llamada. (En telecomunicaciones, el eco es un reflejo del sonido, la misma situación que oirá si se desenlace hasta la parte inferior de un bien). Seleccione una de las siguientes opciones:  <br/> [Todos] Sin eco de marca de tiempo posterior a AEC (cancelación de eco de ruido) ANLP (procesador no lineal adaptable) DNLP (procesador dinámico no lineal) Recorte de micrófono |
|**Tipo de llamada** <br/> |Indica el tipo de llamada que se realizó. Seleccione una de las siguientes opciones:  <br/> [Todos] Llamada de cliente llamada RTC Llamada de conferencia |
|**Tipo de acceso** <br/> |Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [Todos] Interno externo |
|**Tipo de red** <br/> |Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [Todos] Cable inalámbrico |
|**VPN** <br/> |Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [Todos] VPN no VPN |
|**Tipo de dispositivo** <br/> |Indica el tipo de dispositivo. Seleccione una de las siguientes opciones:  <br/> Par de dispositivo de captura y representación de dispositivo de representación de dispositivos de captura |
|**Nombre de dispositivo** <br/> |Nombre del dispositivo de captura o representación. Puedes escribir el nombre completo del dispositivo o cualquier parte del nombre del dispositivo. Por ejemplo, para buscar el micrófono del dispositivo (Microsoft LifeCam VX-1000). Puede escribir el nombre completo del dispositivo de la siguiente manera:  <br/> Micrófono (Microsoft LifeCam VX-1000).  <br/> O bien, puede escribir solo una parte del nombre. Por ejemplo:  <br/> LifeCam  <br/> Tenga en cuenta que el filtro anterior devuelve cualquier dispositivo que contenga la cadena "LifeCam" en cualquier parte de su nombre.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de dispositivos.
  
**Métricas del informe de dispositivos**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Dispositivo de captura** <br/> |Sí  <br/> |Dispositivo (por ejemplo, un micrófono o una cámara web) usado para transmitir audio.  <br/> |
|**Dispositivo de presentación** <br/> |Sí  <br/> |Dispositivo (por ejemplo, auriculares o altavoces) que se usa para recibir audio.  <br/> |
|**Volumen de llamadas** <br/> |Sí  <br/> |Número total de llamadas realizadas.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |Sí  <br/> |Porcentaje de llamadas clasificadas como "deficientes". Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).  <br/> |
|**Usuarios únicos** <br/> |Sí  <br/> |Usuarios únicos que usaron el dispositivo. Si un usuario usó el dispositivo 13 veces, se contará como un usuario único, igual que un usuario que solo usó el dispositivo una sola vez.  <br/> |
|**Relación de tiempo de conmutación de voz** <br/> |Sí  <br/> |Porcentaje de la llamada que se tuvo que realizar en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación puede desplazarse en una sola dirección a la vez, de forma similar a la forma en que los usuarios toman turnos al comunicarse con un walkie-talkie.  <br/> |
|**Relación de micrófono que no funciona** <br/> |Sí  <br/> |Porcentaje de la llamada en la que el dispositivo de captura no funcionaba en un nivel aceptable. Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de captura no funciona como se esperaba.  <br/> |
|**Proporción de altavoz que no funciona** <br/> |Sí  <br/> |Porcentaje de la llamada en la que el dispositivo de representación no funcionaba en un nivel aceptable. Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de representación no funciona como se esperaba.  <br/> |
|**Llamadas con conmutador de voz (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas que se tenían que realizar en modo de dúplex medio. En el modo de dúplex medio, la comunicación puede desplazarse en una sola dirección a la vez, de forma similar a la forma en que los usuarios toman turnos al comunicarse con un walkie-talkie.  <br/> |
|**Micrófono de eco en (%)** <br/> |Sí  <br/> |Porcentaje de tiempo en el que se detectó eco en la secuencia de captura del micrófono. Normalmente, los valores son bajos para auriculares o auriculares, y superiores para los teléfonos de altavoz o los altavoces independientes. En el caso de los dispositivos que admiten la cancelación de ecos de sonido, los valores altos indican pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.  <br/> |
|**Envío de eco (%)** <br/> |Sí  <br/> |Porcentaje de eco transmitido a otros usuarios.  <br/> |
|**Llamadas con eco (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas que tuvieron eco que superó el nivel aceptable.  <br/> |
   

