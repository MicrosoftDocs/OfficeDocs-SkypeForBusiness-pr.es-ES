---
title: 'Lync Server 2013: Informe de inventario de teléfono IP'
TOCTitle: Informe de inventario de teléfono IP
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48276302
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de inventario de teléfono IP en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de inventario de teléfono IP ofrece información sobre los teléfonos IP que la organización usa actualmente. El informe proporciona una lista detallada de los teléfonos IP que realmente se usaron durante el período de informes especificado. Entre otros datos, este informe permite que los administradores conozcan si aún hay teléfonos antiguos obsoletos en uso que se deben reemplazar. También puede advertir a los administradores sobre la presencia de teléfonos costosos que casi no se usan en la organización. Ese tipo de información puede resultar valiosa en el momento de comprar teléfonos nuevos o de redistribuir los teléfonos existentes. (Por ejemplo, se le puede pedir a un usuario que rara vez usa su costoso teléfono que lo intercambie con un usuario que usa el suyo con mucha más frecuencia).

Debe tenerse en cuenta que este informe presenta algunas limitaciones cuando se usa como un informe de inventario real. Por un lado, el informe de inventario de teléfono IP simplemente muestra todos los teléfonos que iniciaron sesión en Lync Server durante el período especificado, ordenados por la hora de último inicio de sesión. Si un teléfono no inició sesión durante el período especificado, no aparecerá en el informe de inventario. Eso incluye los teléfonos que iniciaron sesión antes de que comenzara el período y que seguían conectados durante el intervalo especificado. Por ejemplo, supongamos que desea ver el inventario de teléfonos completo de julio de 2012. Supongamos, además, que varios teléfonos iniciaron sesión en Lync Server el 30 de junio de 2012 y que seguían conectados el 1 de julio. Esos teléfonos no se mostrarán en el informe de inventario del 1 de julio.

También es importante tener en cuenta que el informe de inventario puede incluir teléfonos que la organización ya no usa. Por ejemplo, supongamos que diferentes teléfonos de Fabrikam iniciaron sesión en el sistema el 1 de julio de 2012. Cinco días después, la organización se deshizo de todos esos teléfonos de Fabrikam y los reemplazó por un modelo más nuevo de Contoso. Los teléfonos de Fabrikam seguirán apareciendo en el informe de "inventario" porque iniciaron sesión en el sistema durante el mes de julio.

Además, el informe de inventario de teléfono IP no proporciona información sobre los totales de resumen de los diferentes tipos de teléfonos. Por ejemplo, supongamos que tiene 105 teléfonos Polycom CX600. El informe no indicará que tiene 105 teléfonos de ese tipo; en cambio, simplemente se visualizarán 105 entradas independientes para Polycom CX600. La única forma de saber que existen 105 entradas para Polycom CX600 sería contar cada una de esas entradas manualmente.

> [!WARNING]  
> O bien, exportar los datos y usar Microsoft Excel o Windows PowerShell para que hagan el recuento automáticamente.



## Obtener acceso al informe de inventario de teléfono IP

Se puede tener acceso al informe de inventario de teléfono IP desde la página principal de informes de supervisión. Si hace clic en la métrica URI de usuario, podrá tener acceso al informe de actividad de usuario. Si hace clic en la métrica Última actividad para una llamada punto a punto, podrá ver el informe de detalles de sesiones punto a punto o el informe de detalles de conferencia, si hace clic en la misma métrica para una conferencia.

## Aprovechar al máximo el informe de inventario de teléfono IP

Si solo está interesado en la información de uso de un determinado tipo de teléfono (por ejemplo, "¿Con qué frecuencia se usa un teléfono Polycom CX600?"), puede obtener esa información directamente del informe de inventario de teléfono IP si filtra los datos por ese tipo de teléfono en particular. Sin embargo, si desea información de resumen de todos los teléfonos (cuántas personas usan teléfonos Polycom CX600, cuántas LG-Nortel IP8540, etc.), deberá exportar los datos y usar otra aplicación (como Windows PowerShell) para hacer ese tipo de análisis. Por ejemplo, supongamos que exporta datos a un archivo de valores separados por comas (C:\\Data\\IP\_Phone\_Inventory\_Report.csv). En ese caso, puede usar estos dos comandos para proporcionar datos de resumen de todos los teléfonos:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Se devolverán datos similares a estos:

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

De modo similar, estos dos comandos indican qué teléfonos iniciaron sesión en el sistema, pero nunca se usaron en realidad para hacer llamadas (el valor de la métrica Última actividad está en blanco, lo que indica que no hubo ninguna actividad reciente):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Se devuelven datos similares a estos para cada teléfono que no se usó:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Otra forma interesante de usar el informe de inventario de teléfono IP es la siguiente: si tiene la dirección MAC de un teléfono IP, puede conocer quién usó el teléfono por última vez con solo escribir esa dirección en el cuadro de texto Dirección MAC. El informe luego mostrará, entre otros datos, la dirección SIP del usuario que inició sesión con ese teléfono por última vez. También puede escribir la dirección SIP de un usuario (en el cuadro Prefijo de URI de usuario) para conocer todos los teléfonos que usó ese determinado usuario.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el inventario de teléfonos IP le permite ver solo los teléfonos fabricados por una empresa concreta, o incluso una versión concreta de dichos teléfonos. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.

En la siguiente tabla verá una lista de los filtros que puede usar con el informe de inventario de teléfono IP.

### Filtros del informe de inventario de teléfono IP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Desde</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fabricante</strong></p></td>
<td><p>Nombre de la empresa que fabricó el teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versión de hardware</strong></p></td>
<td><p>Número de versión del teléfono IP. Con los filtros Fabricante y Versión de hardware, podrá identificar de forma única un tipo de teléfono en particular. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario</strong></p></td>
<td><p>Identificador del software del teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dirección MAC</strong></p></td>
<td><p>Identificador único de la interfaz de red del teléfono IP. La dirección Media Access Control (MAC) suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</p>
<p>Para buscar registros correspondientes a una dirección MAC concreta, basta con escribir esa dirección. Por ejemplo:</p>
<p>00-08-5D-16-16-48</p>
<p>Debe escribir la dirección completa. Si escribe parte de una dirección (por ejemplo, 00-08-5D), no obtendrá ningún resultado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Días anteriores a la última actividad</strong></p></td>
<td><p>Seleccione uno de los siguientes valores:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Días anteriores a la hora del último cierre de sesión</strong></p></td>
<td><p>Seleccione uno de los siguientes valores:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Prefijo de URI de usuario</strong></p></td>
<td><p>Dirección SIP del usuario que usó el teléfono IP.</p></td>
</tr>
</tbody>
</table>


## Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de inventario de teléfono IP.

### Métricas del informe de inventario de teléfono IP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fabricante</strong></p></td>
<td><p>Sí</p></td>
<td><p>Nombre de la empresa que fabricó el teléfono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versión de hardware</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número de versión del teléfono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dirección MAC</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador único de la interfaz de red del teléfono IP. La dirección MAC suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de usuario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que usó el teléfono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador del software del teléfono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de último inicio de sesión</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que el teléfono IP inició sesión por última vez en Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de último cierre de sesión</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que el teléfono IP cerró sesión por última vez en Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Última actividad</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se usó por última vez el teléfono IP.</p></td>
</tr>
</tbody>
</table>

