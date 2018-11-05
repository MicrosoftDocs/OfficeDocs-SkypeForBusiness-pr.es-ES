---
title: "Búsquedas en registros de captura creados por el servicio de registro centralizado"
TOCTitle: "Ut. Rech. sur les journaux de capture créés par le service de journ. centr."
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49888907
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de búsquedas en registros de captura creados por el servicio de registro centralizado

 

_**Última modificación del tema:** 2013-02-21_

Las funciones de búsqueda del Servicio de registro centralizado resultan útiles y eficaces por las siguientes razones:

  - Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.

  - Sus búsquedas pueden ser inicialmente amplias y luego acotarse a un criterio más específico como hora, componente o equipo. Al realizar sus búsquedas en los mismos registros, no necesita volver a ejecutar una sesión de registro cuando cambian los criterios de búsqueda.

  - Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitado a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Utiliza herramientas familiares como **Snooper** o **Notepad** para leer el archivo de salida y los mensajes de seguimiento desde su implementación.

El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). Los registros y sus archivos de caché e índice asociados son administrados por el CLSAgent. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información debe recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos de caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController luego agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.

Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía el caché utilizado por búsquedas (que no debe confundirse con los archivos de caché mantenidos por el CLSAgent). Vaciar el caché ayuda a asegurar que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.

Para obtener el mayor beneficio del Servicio de registro centralizado, necesita comprender bien cómo se configura la búsqueda para que devuelva solamente mensajes de seguimiento desde los registros del equipo y los grupos de servidores que son relevantes para la cuestión que está buscando. cuestiones

Para ejecutar las funciones de búsqueda de Servicio de registro centralizado utilizando el Shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o bien CsServerAdministrator, o un rol RBAC personalizado que contenga alguno de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos cualquier rol RBAC personalizado que haya creado usted mismo), ejecute el siguiente comando del Shell de administración de Lync Server o el símbolo del sistema Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto de este tema se centra en cómo definir una búsqueda para optimizar su resolución de problemas.

## Para ejecutar una búsqueda básica utilizando el Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en su implementación en el ámbito global y luego escriba lo siguiente en un símbolo del sistema:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    

    > [!NOTE]
    > Por defecto, Search-CsClsLogging envía los resultados de la búsqueda a la consola. Si desea guardar los resultados de la búsqueda en un archivo, utilice –OutputFilePath <EM>&lt;string fully qualified file path&gt;</EM>. Para definir el parámetro –OutputFilePath, suministre una ruta y un nombre de archivo como parte del parámetro en un formato de cadena encerrado entre comillas (por ejemplo; C:\LogFiles\SearchOutput.txt). En este ejemplo, debe asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS Modificar) de archivos de la carpeta. El resultado se anexa y no se sobreescribe. Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda.

    
    Por ejemplo:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

## Para ejecutar una búsqueda básica en un grupo de servidores o equipo utilizando el Servicio de registro centralizado

1.  Para limitar la búsqueda a un determinado equipo o grupo de servidores, utilice el parámetro –Computers con el equipo definido por un nombre completamente calificado de equipo, encerrado entre comillas y separado por una coma de la siguiente manera:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Por ejemplo:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Para buscar más de un equipo, escriba varios nombres de equipos encerrados entre comillas y separados por comas, como por ejemplo de la siguiente manera:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Si necesita buscar un grupo de servidores entero en lugar de un único equipo, cambie el parámetro –Computers por –Pools, borre le nombre del equipo y reemplácelo con el grupo o los grupos de servidores entre comillas y separados por comas.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Al utilizar los comandos de búsqueda, los grupos de servidores pueden ser cualquier grupo de servidores de su implementación, como Grupos de servidores front-end, Grupos de servidores perimetrales, Grupos de servidores de chat persistente u otros que se definan como grupos de servidores en su implementación.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

## Para ejecutar una búsqueda utilizando los parámetros de hora

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Por defecto, la hora de inicio para los parámetros específicos de hora de una búsqueda es de 30 minutos antes de la hora en que inició la búsqueda. En otras palabras, si inicia su búsqueda a las 16:00:00, la búsqueda se hará sobre los registros para los equipos y grupos de servidores que defina desde las 15:30:00 hasta las 16:00:00. Si necesita buscar desde 60 minutos o 3 horas antes de la hora actual, utilice el parámetro –StartTime y defina la cadena de fecha y hora para indicar la hora en la que quiera que empiece la búsqueda.
    
    Por ejemplo, utilizando los parámetros –StartTime y –EndTime para definir un rango de fecha y hora, puede definir una búsqueda entre las 8 y las 9 del 20/11/2012 en su grupo de servidores. Puede definir la ruta de salida para que escriba los resultados en un archivo llamado c:\\logfile.txt de la manera siguiente:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    

    > [!NOTE]
    > La cadena de fecha y hora que especifique puede ser “fecha hora” u “hora fecha”. El comando analizará la cadena y utilizará los valores apropiados de fecha y hora.



3.  Si desea recuperar registros que comiencen a las 11:00:00 del 20/11/2012, debe definir el parámetro –StartTime. El rango de hora predeterminado para la búsqueda es de 30 minutos a menos que defina un parámetro –EndTime específico. La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.
    
    Por ejemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Para llevar a cabo una búsqueda de registros dentro de un período de tiempo específico, defina un parámetro –StartTime y –EndTime. Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net.
    
    Por ejemplo:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

## Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de coincidencia

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para ejecutar un comando para reunir seguimientos de determinados componentes, escriba lo siguiente:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Por ejemplo:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.

3.  Para limitar la búsqueda con los mismos componentes para solamente su Grupo de servidores front-end llamado pool01.contoso.net, escriba:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos. Puede cambiar este comportamiento especificando el parámetro **–MatchAll**. Para ello, escriba lo siguiente:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder utilizando New-CsClsConfiguration para crear una nueva configuración o modificando una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la serie de registros que se buscarán, utilice el parámetro SkipNetworkLogs de la siguiente manera:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

