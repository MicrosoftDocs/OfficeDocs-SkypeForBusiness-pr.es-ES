---
title: 'Lync Server 2013: informe de inventario de teléfono IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="80822-102">Informe de inventario de teléfono IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80822-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80822-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="80822-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="80822-p101">El informe de inventario de teléfono IP ofrece información sobre los teléfonos IP que la organización usa actualmente. El informe proporciona una lista detallada de los teléfonos IP que realmente se usaron durante el período de informes especificado. Entre otros datos, este informe permite que los administradores conozcan si aún hay teléfonos antiguos obsoletos en uso que se deben reemplazar. También puede advertir a los administradores sobre la presencia de teléfonos costosos que casi no se usan en la organización. Ese tipo de información puede resultar valiosa en el momento de comprar teléfonos nuevos o de redistribuir los teléfonos existentes. (Por ejemplo, se le puede pedir a un usuario que rara vez usa su costoso teléfono que lo intercambie con un usuario que usa el suyo con mucha más frecuencia).</span><span class="sxs-lookup"><span data-stu-id="80822-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="80822-109">Debe tenerse en cuenta que este informe presenta algunas limitaciones cuando se usa como un informe de inventario real.</span><span class="sxs-lookup"><span data-stu-id="80822-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="80822-110">Por un lado, el informe de teléfono IP se limita a enumerar todos los teléfonos que iniciaron sesión en Lync Server durante el período de tiempo especificado, ordenados por la hora de último inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="80822-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="80822-111">Si un teléfono no inició sesión durante el período especificado, no aparecerá en el informe de inventario.</span><span class="sxs-lookup"><span data-stu-id="80822-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="80822-112">Eso incluye los teléfonos que iniciaron sesión antes de que comenzara el período y que seguían conectados durante el intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="80822-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="80822-113">Por ejemplo, supongamos que desea ver el inventario de teléfonos completo de julio de 2012.</span><span class="sxs-lookup"><span data-stu-id="80822-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="80822-114">Supongamos, además, que varios teléfonos iniciaron sesión en Lync Server el 30 de junio de 2012 y que todavía iniciaron sesión a partir del 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="80822-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="80822-115">Esos teléfonos no se mostrarán en el informe de inventario del 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="80822-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="80822-p103">También es importante tener en cuenta que el informe de inventario puede incluir teléfonos que la organización ya no usa. Por ejemplo, supongamos que diferentes teléfonos de Fabrikam iniciaron sesión en el sistema el 1 de julio de 2012. Cinco días después, la organización se deshizo de todos esos teléfonos de Fabrikam y los reemplazó por un modelo más nuevo de Contoso. Los teléfonos de Fabrikam seguirán apareciendo en el informe de "inventario" porque iniciaron sesión en el sistema durante el mes de julio.</span><span class="sxs-lookup"><span data-stu-id="80822-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="80822-p104">Además, el informe de inventario de teléfono IP no proporciona información sobre los totales de resumen de los diferentes tipos de teléfonos. Por ejemplo, supongamos que tiene 105 teléfonos Polycom CX600. El informe no indicará que tiene 105 teléfonos de ese tipo; en cambio, simplemente se visualizarán 105 entradas independientes para Polycom CX600. La única forma de saber que existen 105 entradas para Polycom CX600 sería contar cada una de esas entradas manualmente.</span><span class="sxs-lookup"><span data-stu-id="80822-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="80822-123">O bien, exportar los datos y usar Microsoft Excel o Windows PowerShell para que hagan el recuento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="80822-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="80822-124">Obtener acceso al informe de inventario de teléfono IP</span><span class="sxs-lookup"><span data-stu-id="80822-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="80822-p105">Se puede tener acceso al informe de inventario de teléfono IP desde la página principal de informes de supervisión. Si hace clic en la métrica URI de usuario, podrá tener acceso al informe de actividad de usuario. Si hace clic en la métrica Última actividad para una llamada punto a punto, podrá ver el informe de detalles de sesiones punto a punto o el informe de detalles de conferencia, si hace clic en la misma métrica para una conferencia.</span><span class="sxs-lookup"><span data-stu-id="80822-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="80822-128">Aprovechar al máximo el informe de inventario de teléfono IP</span><span class="sxs-lookup"><span data-stu-id="80822-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="80822-129">Si solo le interesa la información de uso de un tipo de teléfono en particular (por ejemplo, "¿con qué frecuencia usan los usuarios un teléfono Polycom CX600?"), puede obtener esa información directamente del informe de inventario de teléfono IP filtrando para ese tipo de teléfono en particular.</span><span class="sxs-lookup"><span data-stu-id="80822-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="80822-130">Sin embargo, si desea obtener información de Resumen de todos los teléfonos (cuántas personas usan un Polycom CX600, cuántos están usando un IP8540 de LG-Nortel), tendrá que exportar los datos y usar otra aplicación (como Windows PowerShell) para realizar ese tipo de analice.</span><span class="sxs-lookup"><span data-stu-id="80822-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="80822-131">Por ejemplo, supongamos que exporta los datos a un archivo de valores separados por comas\\(\_C\_:\_\\Data IP Phone Inventory Report. csv).</span><span class="sxs-lookup"><span data-stu-id="80822-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="80822-132">En ese caso, podría usar estos dos comandos para proporcionar datos de resumen para todos los teléfonos:</span><span class="sxs-lookup"><span data-stu-id="80822-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="80822-133">Se devolverán datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="80822-133">That will return data similar to this:</span></span>

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

<span data-ttu-id="80822-134">De modo similar, estos dos comandos indican qué teléfonos iniciaron sesión en el sistema, pero nunca se usaron en realidad para hacer llamadas (el valor de la métrica Última actividad está en blanco, lo que indica que no hubo ninguna actividad reciente):</span><span class="sxs-lookup"><span data-stu-id="80822-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="80822-135">Se devuelven datos similares a estos para cada teléfono que no se usó:</span><span class="sxs-lookup"><span data-stu-id="80822-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="80822-136">Otra forma interesante de usar el informe de inventario de teléfono IP es la siguiente: si tiene la dirección MAC de un teléfono IP, puede conocer quién usó el teléfono por última vez con solo escribir esa dirección en el cuadro de texto Dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="80822-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="80822-137">El informe luego mostrará, entre otros datos, la dirección SIP del usuario que inició sesión con ese teléfono por última vez.</span><span class="sxs-lookup"><span data-stu-id="80822-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="80822-138">También puede escribir la dirección SIP de un usuario (en el cuadro Prefijo de URI de usuario) para conocer todos los teléfonos que usó ese determinado usuario.</span><span class="sxs-lookup"><span data-stu-id="80822-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="80822-139">Filtros</span><span class="sxs-lookup"><span data-stu-id="80822-139">Filters</span></span>

<span data-ttu-id="80822-p108">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el inventario de teléfonos IP le permite ver solo los teléfonos fabricados por una empresa concreta, o incluso una versión concreta de dichos teléfonos. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="80822-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="80822-144">En la siguiente tabla verá una lista de los filtros que puede usar con el informe de inventario de teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="80822-145">Filtros del informe de inventario de teléfono IP</span><span class="sxs-lookup"><span data-stu-id="80822-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80822-146">Nombre</span><span class="sxs-lookup"><span data-stu-id="80822-146">Name</span></span></th>
<th><span data-ttu-id="80822-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="80822-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80822-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="80822-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-p109">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="80822-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="80822-151">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="80822-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="80822-p110">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="80822-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="80822-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="80822-154">7/7/2012</span></span></p>
<p><span data-ttu-id="80822-155">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="80822-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="80822-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="80822-156">7/3/2012</span></span></p>
<p><span data-ttu-id="80822-157">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="80822-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="80822-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-p111">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="80822-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="80822-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="80822-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="80822-p112">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="80822-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="80822-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="80822-164">7/7/2012</span></span></p>
<p><span data-ttu-id="80822-165">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="80822-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="80822-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="80822-166">7/3/2012</span></span></p>
<p><span data-ttu-id="80822-167">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="80822-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-168"><strong>Manufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="80822-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-p113">Nombre de la empresa que fabricó el teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="80822-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-171"><strong>Versión de hardware</strong></span><span class="sxs-lookup"><span data-stu-id="80822-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-172">Número de versión del teléfono IP; mediante el uso del fabricante y los filtros de versión de hardware puede identificar de manera única un tipo de teléfono en particular.</span><span class="sxs-lookup"><span data-stu-id="80822-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="80822-173">Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="80822-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-174"><strong>Agente de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="80822-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-p115">Identificador del software del teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="80822-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-177"><strong>Dirección MAC</strong></span><span class="sxs-lookup"><span data-stu-id="80822-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-p116">Identificador único de la interfaz de red del teléfono IP. La dirección Media Access Control (MAC) suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80822-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="80822-p117">Para buscar registros correspondientes a una dirección MAC concreta, basta con escribir esa dirección. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="80822-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="80822-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="80822-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="80822-p118">Debe escribir la dirección completa. Si escribe parte de una dirección (por ejemplo, 00-08-5D), no obtendrá ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="80822-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-185"><strong>Días anteriores a la última actividad</strong></span><span class="sxs-lookup"><span data-stu-id="80822-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-186">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="80822-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="80822-187">Todos</span><span class="sxs-lookup"><span data-stu-id="80822-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="80822-188">10 </span><span class="sxs-lookup"><span data-stu-id="80822-188">10</span></span></p></li>
<li><p><span data-ttu-id="80822-189">20</span><span class="sxs-lookup"><span data-stu-id="80822-189">20</span></span></p></li>
<li><p><span data-ttu-id="80822-190">semestre</span><span class="sxs-lookup"><span data-stu-id="80822-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-191"><strong>Días anteriores a la hora del último cierre de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="80822-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-192">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="80822-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="80822-193">Todos</span><span class="sxs-lookup"><span data-stu-id="80822-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="80822-194">10 </span><span class="sxs-lookup"><span data-stu-id="80822-194">10</span></span></p></li>
<li><p><span data-ttu-id="80822-195">20</span><span class="sxs-lookup"><span data-stu-id="80822-195">20</span></span></p></li>
<li><p><span data-ttu-id="80822-196">semestre</span><span class="sxs-lookup"><span data-stu-id="80822-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-197"><strong>Prefijo de URI de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="80822-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-198">Dirección SIP del usuario que usó el teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="80822-199">Métricas</span><span class="sxs-lookup"><span data-stu-id="80822-199">Metrics</span></span>

<span data-ttu-id="80822-200">En la tabla siguiente se muestra la información proporcionada en el informe de inventario de teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="80822-201">Métricas del informe de inventario de teléfono IP</span><span class="sxs-lookup"><span data-stu-id="80822-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80822-202">Nombre</span><span class="sxs-lookup"><span data-stu-id="80822-202">Name</span></span></th>
<th><span data-ttu-id="80822-203">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="80822-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="80822-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="80822-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80822-205"><strong>Manufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="80822-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-206">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-207">Nombre de la empresa que fabricó el teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-208"><strong>Versión de hardware</strong></span><span class="sxs-lookup"><span data-stu-id="80822-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-209">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-210">Número de versión del teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-211"><strong>Dirección MAC</strong></span><span class="sxs-lookup"><span data-stu-id="80822-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-212">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-p119">Identificador único de la interfaz de red del teléfono IP. La dirección MAC suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80822-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-215"><strong>URI de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="80822-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-216">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-217">Dirección SIP del usuario que usó el teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-218"><strong>Agente de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="80822-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-219">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-220">Identificador del software del teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-221"><strong>Hora de último inicio de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="80822-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-222">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-223">Fecha y hora en que el teléfono IP inició sesión por última vez en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80822-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80822-224"><strong>Hora de último cierre de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="80822-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-225">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-226">Fecha y hora en que el teléfono IP cerró sesión por última vez en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80822-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80822-227"><strong>Última actividad</strong></span><span class="sxs-lookup"><span data-stu-id="80822-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="80822-228">Sí</span><span class="sxs-lookup"><span data-stu-id="80822-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="80822-229">Fecha y hora en que se usó por última vez el teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="80822-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

