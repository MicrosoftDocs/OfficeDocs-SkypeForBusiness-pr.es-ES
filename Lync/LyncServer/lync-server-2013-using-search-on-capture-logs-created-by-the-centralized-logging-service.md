---
title: Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9571f2efe08eb13091c3d3660e7760a8e805c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Las características de búsqueda del servicio de registro centralizado son útiles y eficaces por las siguientes razones:

  - Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.

  - Sus búsquedas pueden ser inicialmente amplias y luego acotarse a un criterio más específico como hora, componente o equipo. Al realizar sus búsquedas en los mismos registros, no necesita volver a ejecutar una sesión de registro cuando cambian los criterios de búsqueda.

  - Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitado a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Utiliza herramientas familiares como **Snooper** o **Notepad** para leer el archivo de salida y los mensajes de seguimiento desde su implementación.

El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). Los registros y sus archivos de caché e índice asociados son administrados por el CLSAgent. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información debe recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos de caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController luego agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.

Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía el caché utilizado por búsquedas (que no debe confundirse con los archivos de caché mantenidos por el CLSAgent). Vaciar el caché ayuda a asegurar que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.

Para sacar el máximo partido del servicio de registro centralizado, necesita comprender mejor cómo configurar la búsqueda para que devuelva solo los mensajes de seguimiento del equipo y los registros de grupo que son relevantes para el problema que está investigando. aspectos

Para ejecutar las funciones de búsqueda del servicio de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto de este tema se centra en cómo definir una búsqueda para optimizar su resolución de problemas.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica mediante el servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en su implementación en el ámbito global y luego escriba lo siguiente en un símbolo del sistema:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Por defecto, Search-CsClsLogging envía los resultados de la búsqueda a la consola. Si desea guardar los resultados de la búsqueda en un archivo, use la ruta &lt;de acceso&gt;completa del archivo de cadena de OutputFilePath. Para definir el parámetro –OutputFilePath, suministre una ruta y un nombre de archivo como parte del parámetro en un formato de cadena encerrado entre comillas (por ejemplo; C:\LogFiles\SearchOutput.txt). En este ejemplo, debe asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS Modificar) de archivos de la carpeta. El resultado se anexa y no se sobreescribe. Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda.

    
    </div>
    
    Por ejemplo:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica en un grupo o un equipo con el servicio de registro centralizado

1.  Para limitar la búsqueda a un determinado equipo o grupo de servidores, utilice el parámetro –Computers con el equipo definido por un nombre completamente calificado de equipo, encerrado entre comillas y separado por una coma de la siguiente manera:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Por ejemplo:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Para buscar más de un equipo, escriba varios nombres de equipos encerrados entre comillas y separados por comas, como por ejemplo de la siguiente manera:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Si necesita buscar un grupo de servidores entero en lugar de un único equipo, cambie el parámetro –Computers por –Pools, borre le nombre del equipo y reemplácelo con el grupo o los grupos de servidores entre comillas y separados por comas.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Cuando se usan los comandos de búsqueda, los grupos de servidores pueden ser cualquier grupo de la implementación, como los grupos de servidores front-end, los grupos de servidores perimetrales, los grupos de servidores de chat persistente u otros definidos como grupo en la implementación.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>Para ejecutar una búsqueda utilizando los parámetros de hora

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Por defecto, la hora de inicio para los parámetros específicos de hora de una búsqueda es de 30 minutos antes de la hora en que inició la búsqueda. En otras palabras, si inicia su búsqueda a las 16:00:00, la búsqueda se hará sobre los registros para los equipos y grupos de servidores que defina desde las 15:30:00 hasta las 16:00:00. Si necesita buscar desde 60 minutos o 3 horas antes de la hora actual, utilice el parámetro –StartTime y defina la cadena de fecha y hora para indicar la hora en la que quiera que empiece la búsqueda.
    
    Por ejemplo, utilizando los parámetros –StartTime y –EndTime para definir un rango de fecha y hora, puede definir una búsqueda you entre las 8 y las 9 del 20/11/2012 en su grupo de servidores. Puede establecer la ruta de acceso de los resultados para escribir los resultados en un archivo\\denominado c: logfile. txt de la siguiente manera:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > La cadena de fecha y hora que especifique puede ser "fecha y hora" o "fecha de fecha y hora. "El comando analizará la cadena y usará los valores apropiados para la fecha y la hora.

    
    </div>

3.  Si desea recuperar registros que comiencen a las 11:00:00 del 20/11/2012, debe definir el parámetro –StartTime. El rango de hora predeterminado para la búsqueda es de 30 minutos a menos que defina un parámetro –EndTime específico. La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Para llevar a cabo una búsqueda de registros dentro de un período de tiempo específico, defina un parámetro –StartTime y –EndTime. Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net.
    
    Por ejemplo:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de coincidencia

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Para ejecutar un comando para reunir seguimientos de determinados componentes, escriba lo siguiente:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Por ejemplo:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.

3.  Para limitar la búsqueda con los mismos componentes solo a su grupo de servidores front-end denominado pool01.contoso.net, escriba:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos. Puede cambiar este comportamiento especificando el parámetro **–MatchAll**. Para ello, escriba lo siguiente:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder utilizando New-CsClsConfiguration para crear una nueva configuración o modificando una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la serie de registros que se buscarán, utilice el parámetro SkipNetworkLogs de la siguiente manera:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

