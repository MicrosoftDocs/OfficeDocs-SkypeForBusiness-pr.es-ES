---
title: Informe de inventario de teléfono IP en Skype Empresarial Server
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
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Resumen: obtenga información sobre el informe de inventario de teléfono IP en Skype Empresarial Server.'
ms.openlocfilehash: 513b4ac54cf337a13cd95523fa3de750ce5f8c17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823460"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Informe de inventario de teléfono IP en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de inventario de teléfono IP en Skype Empresarial Server.
  
El informe de inventario de teléfono IP ofrece información sobre los teléfonos IP que la organización usa actualmente. El informe proporciona una lista detallada de los teléfonos IP que realmente se usaron durante el período de informes especificado. Entre otros datos, este informe permite que los administradores conozcan si aún hay teléfonos antiguos obsoletos en uso que se deben reemplazar. También puede advertir a los administradores sobre la presencia de teléfonos costosos que casi no se usan en la organización. Ese tipo de información puede resultar valiosa en el momento de comprar teléfonos nuevos o de redistribuir los teléfonos existentes. (Por ejemplo, se le puede pedir a un usuario que rara vez usa su costoso teléfono que lo intercambie con un usuario que usa el suyo con mucha más frecuencia).
  
Debe tenerse en cuenta que este informe presenta algunas limitaciones cuando se usa como un informe de inventario real. Por un lado, el informe de teléfono IP simplemente enumera todos los teléfonos que iniciaron sesión en Skype Empresarial Server durante el período de tiempo especificado, ordenados por la hora de su último inicio de sesión. Si un teléfono no inició sesión durante el período especificado, no aparecerá en el informe de inventario. Eso incluye los teléfonos que iniciaron sesión antes de que comenzara el período y que seguían conectados durante el intervalo especificado. Por ejemplo, supongamos que quiere ver todo el inventario de teléfonos de julio de 2015. Supongamos, además, que varios teléfonos iniciaron sesión en Skype Empresarial Server el 30 de junio de 2015 y aún habían iniciado sesión a partir del 1 de julio. Esos teléfonos no se mostrarán en el informe de inventario del 1 de julio.
  
También es importante tener en cuenta que el informe de inventario podría incluir teléfonos que su organización ya no usa. Por ejemplo, supongamos que varios teléfonos Fabrikam iniciaron sesión en el sistema el 1 de julio de 2015; 5 días después, su organización se deshizo de todos los teléfonos Fabrikam y los reemplazó por un modelo Contoso más reciente. Los teléfonos Fabrikam seguirán apareciendo en el informe de "inventario" simplemente porque iniciaron sesión en el sistema durante el mes de julio.
  
Además, el informe de inventario de teléfono IP no proporciona información sobre los totales de resumen de los diferentes tipos de teléfonos. Por ejemplo, supongamos que tiene 105 teléfonos Polycom CX600. El informe no indicará que tiene 105 teléfonos de ese tipo; en cambio, simplemente se visualizarán 105 entradas independientes para Polycom CX600. La única forma de saber que existen 105 entradas para Polycom CX600 sería contar cada una de esas entradas manualmente.
  
> [!TIP]
> O bien, exportar los datos y usar Microsoft Excel o Windows PowerShell para que hagan el recuento automáticamente. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Obtener acceso al informe de inventario de teléfono IP

Se puede tener acceso al informe de inventario de teléfono IP desde la página principal de informes de supervisión. Si hace clic en la métrica URI de usuario, podrá tener acceso al informe de actividad de usuario. Si hace clic en la métrica Última actividad para una llamada punto a punto, podrá ver el informe de detalles de sesiones punto a punto o el informe de detalles de conferencia, si hace clic en la misma métrica para una conferencia.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Aprovechar al máximo el informe de inventario de teléfono IP

Si solo está interesado en la información de uso de un determinado tipo de teléfono (por ejemplo, "¿Con qué frecuencia se usa un teléfono Polycom CX600?"), puede obtener esa información directamente del informe de inventario de teléfono IP si filtra los datos por ese tipo de teléfono en particular. Sin embargo, si desea información de resumen de todos los teléfonos (cuántas personas usan teléfonos Polycom CX600, cuántas LG-Nortel IP8540, etc.), deberá exportar los datos y usar otra aplicación (como Windows PowerShell) para hacer ese tipo de análisis. Por ejemplo, supongamos que exporta datos a un archivo de valores separados por comas (C:\Data\IP_Phone_Inventory_Report.csv). En ese caso, puede usar estos dos comandos para proporcionar datos de resumen de todos los teléfonos:
  
```PowerShell
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
  
```PowerShell
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

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Fabricante** <br/> |Nombre de la empresa que fabricó el teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Versión de hardware** <br/> |Número de versión del teléfono IP; mediante el uso de los filtros fabricante y de versión de hardware, puede identificar de forma única un tipo determinado de teléfono. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Agente de usuario** <br/> |Identificador del software del teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.  <br/> |
|**Dirección MAC** <br/> |Identificador único de la interfaz de red del teléfono IP. La dirección Media Access Control (MAC) suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.  <br/> Para buscar registros correspondientes a una dirección MAC concreta, basta con escribir esa dirección. Por ejemplo:  <br/> 00-08-5D-16-16-48  <br/> Debe escribir la dirección completa. Si escribe parte de una dirección (por ejemplo, 00-08-5D), no obtendrá ningún resultado.  <br/> |
|**Días anteriores a la última actividad** <br/> | Seleccione uno de los siguientes valores: <br/>  [Todos] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Días anteriores a la hora del último cierre de sesión** <br/> | Seleccione uno de los siguientes valores: <br/>  [Todos] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Prefijo de URI de usuario** <br/> |Dirección SIP del usuario que usó el teléfono IP.  <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de inventario de teléfono IP.
  
**Métricas del informe de inventario de teléfono IP**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Fabricante** <br/> |Sí  <br/> |Nombre de la empresa que fabricó el teléfono IP.  <br/> |
|**Versión de hardware** <br/> |Sí  <br/> |Número de versión del teléfono IP.  <br/> |
|**Dirección MAC** <br/> |Sí  <br/> |Identificador único de la interfaz de red del teléfono IP. La dirección MAC suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.  <br/> |
|**URI de usuario** <br/> |Sí  <br/> |Dirección SIP del usuario que usó el teléfono IP.  <br/> |
|**Agente de usuario** <br/> |Sí  <br/> |Identificador del software del teléfono IP.  <br/> |
|**Hora de último inicio de sesión** <br/> |Sí  <br/> |Fecha y hora en que el teléfono IP inició sesión por última vez en Skype Empresarial Server.  <br/> |
|**Hora de último cierre de sesión** <br/> |Sí  <br/> |Fecha y hora en que el teléfono IP finalmente ha cerrado sesión en Skype Empresarial Server.  <br/> |
|**Última actividad** <br/> |Sí  <br/> |Fecha y hora en que se usó por última vez el teléfono IP.  <br/> |
   

