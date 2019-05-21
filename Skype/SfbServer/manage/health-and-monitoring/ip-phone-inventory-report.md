---
title: Informe de inventario telefónico de IP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Resumen: Obtenga información sobre el informe de inventario telefónico de IP en Skype empresarial Server.'
ms.openlocfilehash: 8d7d7be6b5a677f3df33ebf2e0bb01f31b76eac9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305671"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Informe de inventario telefónico de IP en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de inventario telefónico de IP en Skype empresarial Server.
  
El informe de inventario de teléfono IP ofrece información sobre los teléfonos IP que la organización usa actualmente. El informe proporciona una lista detallada de los teléfonos IP que realmente se usaron durante el período de informes especificado. Entre otros datos, este informe permite que los administradores conozcan si aún hay teléfonos antiguos obsoletos en uso que se necesiten reemplazar. También puede advertir a los administradores sobre la presencia de teléfonos costosos que casi no se usan en la organización. Ese tipo de información puede resultar valiosa en el momento de comprar teléfonos nuevos o de redistribuir los teléfonos existentes. (Por ejemplo, se le puede pedir a un usuario que rara vez usa su costoso teléfono que lo intercambie con un usuario que usa el suyo con mucha más frecuencia).
  
Es preciso tener en cuenta que este informe presenta algunas limitaciones cuando se usa como un informe de inventario real. Por un lado, el informe de teléfono IP simplemente muestra todos los teléfonos que han iniciado sesión en Skype empresarial Server durante el período de tiempo especificado, ordenados por el último tiempo de inicio de sesión. Si un teléfono no inició sesión durante el período especificado, no aparecerá en el informe de inventario. Eso incluye los teléfonos que iniciaron sesión antes de que comenzara el período y que seguían conectados durante el intervalo especificado. Por ejemplo, supongamos que desea ver el inventario de teléfonos completo de julio de 2015. Supongamos, además, que varios teléfonos han iniciado sesión en Skype empresarial Server el 30 de junio de 2015 y que aún no han iniciado sesión a partir del 1 de julio. Esos teléfonos no se mostrarán en el informe de inventario del 1 de julio.
  
También es importante tener en cuenta que el informe de inventario puede incluir teléfonos que la organización ya no usa. Por ejemplo, supongamos que diferentes teléfonos de Fabrikam iniciaron sesión en el sistema el miércoles, 01 de julio de 2015. Cinco días después, la organización se deshizo de todos esos teléfonos de Fabrikam y los reemplazó por un modelo más nuevo de Contoso. Los teléfonos de Fabrikam seguirán apareciendo en el informe de "inventario" porque iniciaron sesión en el sistema durante el mes de julio.
  
Además, el informe de inventario de teléfono IP no proporciona información sobre los totales de resumen de los diferentes tipos de teléfonos. Por ejemplo, supongamos que tiene 105 teléfonos Polycom CX600. El informe no indicará que tiene 105 teléfonos de ese tipo; en cambio, simplemente se visualizarán 105 entradas independientes para Polycom CX600. La única forma de saber que existen 105 entradas para Polycom CX600 sería contar cada una de esas entradas manualmente.
  
> [!TIP]
> O bien, exportar los datos y usar Microsoft Excel o Windows PowerShell para que hagan el recuento automáticamente. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Obtener acceso al informe de inventario de teléfono IP

Se puede tener acceso al informe de inventario de teléfono IP desde la página principal de informes de supervisión. Si hace clic en la métrica URI de usuario, podrá tener acceso al informe de actividad de usuario. Si hace clic en la métrica Última actividad para una llamada punto a punto, podrá ver el informe de detalles de sesiones punto a punto o el informe de detalles de conferencia, si hace clic en la misma métrica para una conferencia.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Aprovechar al máximo el informe de inventario de teléfono IP

Si solo está interesado en la información de uso de un determinado tipo de teléfono (por ejemplo, "¿Con qué frecuencia se usa un teléfono Polycom CX600?"), puede obtener esa información directamente del informe de inventario de teléfono IP si filtra los datos por ese tipo de teléfono en particular. Pero, si desea información de resumen de todos los teléfonos (cuántas personas usan teléfonos Polycom CX600, cuántas LG-Nortel IP8540, etc.), tendrá que exportar los datos y usar otra aplicación (como Windows PowerShell) para hacer ese tipo de análisis. Por ejemplo, supongamos que exporta datos a un archivo de valores separados por comas (C:\Data\IP_Phone_Inventory_Report.csv). En ese caso, puede usar estos dos comandos para proporcionar datos de resumen de todos los teléfonos:
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Se devolverán datos similares a estos:
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

De modo similar, estos dos comandos indican qué teléfonos iniciaron sesión en el sistema, pero nunca se usaron en realidad para hacer llamadas (el valor de la métrica Última actividad está en blanco, lo que indica que no hubo ninguna actividad reciente):
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

Se devuelven datos similares a estos para cada teléfono que no se usó:
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

Otra forma interesante de usar el informe de inventario de teléfono IP es la siguiente: si tiene la dirección MAC de un teléfono IP, puede conocer quién usó el teléfono por última vez con solo escribir esa dirección en el cuadro de texto Dirección MAC. El informe luego mostrará, entre otros datos, la dirección SIP del usuario que inició sesión con ese teléfono por última vez. También puede escribir la dirección SIP de un usuario (en el cuadro Prefijo de URI de usuario) para conocer todos los teléfonos que usó ese determinado usuario.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el inventario de teléfonos IP le permite ver solo los teléfonos fabricados por una empresa concreta, o incluso una versión concreta de dichos teléfonos. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.
  
En la siguiente tabla verá una lista de los filtros que puede usar con el informe de inventario de teléfono IP.
  
**Filtros del informe de inventario de teléfono IP**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Fabricante** <br/> |Nombre de la empresa que fabricó el teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Versión de hardware** <br/> |Número de versión del teléfono IP. con el fabricante y los filtros de versión de hardware, puede identificar de manera inequívoca un determinado tipo de teléfono. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Agente de usuario** <br/> |Identificador del software del teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Dirección MAC** <br/> |Identificador único de la interfaz de red del teléfono IP. La dirección Media Access Control (MAC) suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.  <br/> Para buscar registros correspondientes a una dirección MAC concreta, basta con escribir esa dirección. Por ejemplo:  <br/> 00-08-5D-16-16-48  <br/> Necesita escribir la dirección completa. Si escribe parte de una dirección (por ejemplo, 00-08-5D), no obtendrá ningún resultado.  <br/> |
|**Días anteriores a la última actividad** <br/> | Seleccione uno de los siguientes valores: <br/>  [Todas] <br/>  base10 <br/>  veinte <br/>  0,30 <br/> |
|**Días anteriores a la hora del último cierre de sesión** <br/> | Seleccione uno de los siguientes valores: <br/>  [Todas] <br/>  base10 <br/>  veinte <br/>  0,30 <br/> |
|**Prefijo de URI de usuario** <br/> |Dirección SIP del usuario que usó el teléfono IP.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de inventario de teléfono IP.
  
**Métricas del informe de inventario de teléfono IP**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Fabricante** <br/> |Sí  <br/> |Nombre de la empresa que fabricó el teléfono IP.  <br/> |
|**Versión de hardware** <br/> |Sí  <br/> |Número de versión del teléfono IP.  <br/> |
|**Dirección MAC** <br/> |Sí  <br/> |Identificador único de la interfaz de red del teléfono IP. La dirección MAC suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.  <br/> |
|**URI de usuario** <br/> |Sí  <br/> |Dirección SIP del usuario que usó el teléfono IP.  <br/> |
|**Agente de usuario** <br/> |Sí  <br/> |Identificador del software del teléfono IP.  <br/> |
|**Hora del último inicio de sesión** <br/> |Sí  <br/> |Fecha y hora en que el teléfono IP ha iniciado sesión en Skype empresarial Server.  <br/> |
|**Hora del último cierre de sesión** <br/> |Sí  <br/> |Fecha y hora en que el teléfono IP se cerró por última vez en Skype empresarial Server.  <br/> |
|**Última actividad** <br/> |Sí  <br/> |Fecha y hora en que se usó por última vez el teléfono IP.  <br/> |
   

