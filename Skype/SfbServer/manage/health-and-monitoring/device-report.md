---
title: Informe de dispositivos en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Resumen: Información sobre el informe de dispositivos en Skype para Business Server.'
ms.openlocfilehash: 27b67c75184a7c56e72c0d2ee5953f90e161f20d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926651"
---
# <a name="device-report-in-skype-for-business-server"></a>Informe de dispositivos en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de dispositivos en Skype para Business Server.
  
El informe de dispositivos tendría que llamarse más bien Informe de micrófono y altavoces porque el informe de dispositivos recupera las métricas relacionadas con las llamadas (como porcentaje de llamadas deficientes, eco y tiempo de conmutación de voz) agrupadas por los micrófonos y los altavoces utilizados durante la llamada. Si está interesado en los teléfonos IP (también conocido comúnmente como "dispositivos"), use el [Informe de inventario de teléfono IP en Skype para Business Server](ip-phone-inventory-report.md) en su lugar.
  
El informe de dispositivos es muy útil para los administradores a la hora de determinar si un tipo concreto de dispositivo está sufriendo un número de llamadas de calidad deficiente superior al de otros. A su vez, puede influir en las decisiones que se tomen respecto a comprar nuevos dispositivos o sustituir los actuales.
  
De forma predeterminada, la información mostrada en el informe de dispositivos también atañe al micrófono (el dispositivo de captura) y los altavoces o auriculares (los dispositivos de presentación) empleados durante la llamada. Por ejemplo, si hay varios usuarios que utilizan el siguiente dispositivo de captura y el siguiente dispositivo de presentación:
  
- Dispositivo de captura: micrófono (audio HD digital integrado SoundMAX)
    
- Dispositivo de presentación: auriculares (Microsoft LifeChat LX-3000)
    
Si estos usuarios realizaron un total de 254 llamadas, verá una entrada como la siguiente en el informe:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Ahora, supongamos que tiene una serie de usuarios que utilizan ese mismo dispositivo de captura, pero un dispositivo de presentación diferente. En ese caso, tendrá una segunda entrada en el informe referente a esta combinación única de dispositivo de captura y dispositivo de presentación:
  
|**Dispositivo de captura**|**Dispositivo de presentación**|**Volumen de llamadas**|
|:-----|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Auriculares (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |Altavoces (Audio HD digital integrado SoundMAX)  <br/> |319  <br/> |
   
Si prefiere ver los totales combinados de un dispositivo concreto (por ejemplo, del dispositivo de captura SoundMAX, independientemente de cual sea el dispositivo de presentación utilizado), seleccione la opción correspondiente en la lista desplegable Tipo de dispositivo (a saber, Dispositivo de captura o Dispositivo de presentación). Si selecciona dispositivo de captura, por ejemplo, el resultado será similar a:
  
|**Dispositivo de captura**|**Volumen de llamadas**|
|:-----|:-----|
|Micrófono (Audio HD digital integrado SoundMAX)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Acceso al informe de dispositivos

Generalmente, se accede al informe de dispositivos desde la página de inicio de Informes de supervisión. Sin embargo, si está viendo el [Informe de detalles de llamadas en Skype para Business Server](call-detail-report.md) puede navegar hasta el informe de dispositivos para un dispositivo específico, haga clic en cualquiera de las métricas siguientes:
  
- Dispositivo de captura
    
- Dispositivo de presentación
    
Desde el informe de dispositivo puede navegar hasta el [Informe de lista de llamadas en Skype para Business Server](call-list-report-0.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Volumen de llamadas
    
- Porcentaje de llamadas deficientes
    
## <a name="making-the-best-use-of-the-device-report"></a>Aprovechamiento del informe de dispositivos

En lo que se refiere a los nombres de dispositivos, el informe de dispositivos es muy detallado. Por ejemplo, supongamos que tiene los siguientes dispositivos de captura:
  
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
    
- Micrófono Aastra 6725ip (USB Audio Device)
    
- Micrófono Aastra 6725ip (USB Audio Device)-V0
    
> [!NOTE]
> Tenga en cuenta que los nombres de dispositivo de captura pueden no ser el mismo si está ejecutando las versiones localizadas de Skype para Business Server. El dispositivo Aastra 6725ip Microphone (Aastra 6725ip)-V0 en inglés, podría tener otro nombre en francés o en español. 
  
Habrá casos en los que desee trabajar con ese nivel de detalles, pero habrá otros en los que solo le interese saber cuántas llamadas utilizaron un micrófono Aastra, sea cual sea, sin importar el número de modelo. Una forma de obtener esta información es exportar los datos del informe de dispositivos a Microsoft Excel y, entonces, guardar los datos en un archivo de valores separados por coma (por ejemplo, C:\Data\Devices_Report.csv). A continuación, podrá utilizar un conjunto de comandos similar al siguiente para importar el archivo .CSB en Windows PowerShell y crear un informe del total de llamadas realizadas con un dispositivo de captura Aastra:
  
```
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Así se devolverá un único valor correspondiente al número total de llamadas realizadas con un dispositivo de captura Aastra. Por ejemplo: 384

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de dispositivos permite filtrar elementos como el tipo de llamada (es decir, si la llamada era de un cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC). También se puede elegir cómo agrupar los datos. En este caso, los dispositivos se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de dispositivos.
  
**Filtros del informe de dispositivos**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Causa de la conmutación de voz** <br/> |Motivo por el que se tuvo que realizar una llamada en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, es similar al modo por turnos utilizado para comunicarse con un walkie-talkie. Seleccione una de las siguientes opciones:  <br/> [All] Ninguno eco posterior a AEC (cancelación del eco acústico) del estado de dispositivo incorrecto de complejidad baja marca de tiempo incorrecta, eco DNLP (procesador no lineal dinámico) |
|**Causa del eco** <br/> |Motivo por el que se ha detectado en una llamada un eco que supera el nivel aceptado (en las telecomunicaciones, el eco es un reflejo del sonido, el mismo fenómeno que se produce cuando se grita en un pozo). Seleccione una de las siguientes opciones:  <br/> [All] Ninguna marca de tiempo incorrecta posterior a AEC eco de recorte de ANLP (procesador no lineal adaptable) DNLP (procesador no lineal dinámico) micrófono (cancelación del eco acústico) |
|**Tipo de llamada** <br/> |Indica el tipo de llamada realizada. Seleccione una de las siguientes opciones:  <br/> [All] Llamada de cliente RTC llamada llamada de conferencia |
|**Tipo de acceso** <br/> |Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] Internos externos |
|**Tipo de red** <br/> |Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] Cable e inalámbrica |
|**VPN** <br/> |Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:  <br/> [All] VPN distinta de VPN |
|**Tipo de dispositivo** <br/> |Indica el tipo de dispositivo. Seleccione una de las siguientes opciones:  <br/> Capturar a pareja de dispositivos de dispositivo Render dispositivo de captura/presentación |
|**Nombre del dispositivo** <br/> |Nombre del dispositivo de captura o presentación. Puede escribir el nombre completo del dispositivo o cualquier parte del mismo. Por ejemplo, para encontrar el dispositivo Micrófono (Microsoft LifeCam VX-1000), puede escribir el nombre completo del dispositivo del modo siguiente:  <br/> Micrófono (Microsoft LifeCam VX-1000)  <br/> También puede escribir solo una parte del nombre. Por ejemplo:  <br/> LifeCam  <br/> Tenga en cuenta que el filtro anterior devolverá cualquier dispositivo que contenga la cadena "LifeCam" en cualquier parte del nombre.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información que recoge el informe de dispositivos.
  
**Métricas del informe de dispositivos**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Dispositivo de captura** <br/> |Sí  <br/> |Dispositivo (por ejemplo, un micrófono o una cámara web) utilizado para transmitir audio.  <br/> |
|**Dispositivo de presentación** <br/> |Sí  <br/> |Dispositivo (por ejemplo, unos auriculares o altavoces) utilizado para recibir audio.  <br/> |
|**Volumen de llamadas** <br/> |Sí  <br/> |Cantidad total de llamadas realizadas.  <br/> |
|**Porcentaje de llamadas deficientes** <br/> |Sí  <br/> |Porcentaje de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.  <br/> |
|**Usuarios únicos** <br/> |Sí  <br/> |Usuarios únicos que han utilizado el dispositivo. Si un usuario ha utilizado el dispositivo 13 veces, se contará como un usuario único, igual que un usuario que solo haya utilizado el dispositivo una única vez.  <br/> |
|**Relación de tiempo de conmutación de voz** <br/> |Sí  <br/> |Porcentaje de la llamada que se ha tenido que realizar en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, similar al modo por turnos utilizado para comunicarse con un walkie-talkie.  <br/> |
|**Relación de tiempo durante el que el micrófono estuvo sin funcionar** <br/> |Sí  <br/> |Porcentaje de la llamada en el que el dispositivo de captura no funcionaba a un nivel aceptable. Un valor elevado sugiere que los problemas de calidad de la llamada se deben principalmente a que el dispositivo de captura no funciona como debería.  <br/> |
|**Relación de tiempo durante el que el altavoz estuvo sin funcionar** <br/> |Sí  <br/> |Porcentaje de la llamada en el que el dispositivo de presentación no funcionaba a un nivel aceptable. Un valor elevado sugiere que los problemas de calidad de la llamada se deben principalmente a que el dispositivo de presentación no funciona como debería.  <br/> |
|**Llamadas con conmutación de voz (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas que se han tenido que realizar en modo de dúplex medio. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, algo similar al modo por turnos utilizado para comunicarse con un walkie-talkie.  <br/> |
|**Eco del micrófono en (%)** <br/> |Sí  <br/> |Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.  <br/> |
|**Envío de eco (%)** <br/> |Sí  <br/> |Porcentaje de eco transmitido a otros usuarios.  <br/> |
|**Llamadas con eco (%)** <br/> |Sí  <br/> |Porcentaje del total de llamadas cuyo eco superaba el nivel aceptable.  <br/> |
   

