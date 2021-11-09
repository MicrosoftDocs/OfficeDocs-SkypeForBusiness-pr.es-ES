---
title: Registros de captura de búsqueda creados por el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Summary: Learn how to search and read Centralized Logging Service capture logs in Skype Empresarial Server 2015.'
ms.openlocfilehash: a65fac6ffc96088cd1e544ed17914128d040e2b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831924"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Registros de captura de búsqueda creados por el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo buscar y leer registros de captura del servicio de registro centralizado en Skype Empresarial Server 2015.
  
Las características de búsqueda del servicio de registro centralizado son útiles y eficaces por los siguientes motivos: 
  
- Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.
    
- Sus búsquedas pueden ser inicialmente amplias y luego acotarse a un criterio más específico como hora, componente o equipo. Busca en los mismos registros y no es necesario volver a ejecutar una sesión de registro cuando cambien los criterios de búsqueda.
    
- Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitado a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Utiliza herramientas familiares como **Snooper** o **Notepad** para leer el archivo de salida y los mensajes de seguimiento desde su implementación.
    
El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). Los registros y sus archivos de caché e índice asociados son administrados por el CLSAgent. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información debe recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos de caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController luego agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.
  
Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía el caché utilizado por búsquedas (que no debe confundirse con los archivos de caché mantenidos por el CLSAgent). Vaciar el caché ayuda a asegurar que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.
  
Para obtener la mayor ventaja del servicio de registro centralizado, necesita una buena comprensión de cómo configurar la búsqueda para devolver solo mensajes de seguimiento del equipo y los registros del grupo que son relevantes para el problema que está investigando. problemas
  
Para ejecutar las funciones de búsqueda del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC) o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o el símbolo del sistema Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir una búsqueda para optimizar su resolución de problemas.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica mediante el servicio de registro centralizado

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en su implementación en el ámbito global y luego escriba lo siguiente en un símbolo del sistema:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Por defecto, Search-CsClsLogging envía los resultados de la búsqueda a la consola. Si desea guardar los resultados de la búsqueda en un archivo, use -OutputFilePath  _\<string fully qualified file path\>_ . Para definir el parámetro -OutputFilePath, proporcione una ruta de acceso y un nombre de archivo como parte del parámetro en un formato de cadena entre comillas (por ejemplo, C:\LogFiles\SearchOutput.txt). En este ejemplo, debe asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS Modificar) de archivos de la carpeta. El resultado se anexa y no se sobreescribe. Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda. 
  
Por ejemplo:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica en un grupo o equipo mediante el servicio de registro centralizado

1. Para limitar la búsqueda a un grupo o equipo específico, use el parámetro -Computers con el equipo definido por un nombre completo del equipo, entre comillas y separado por una coma de la siguiente manera:
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Por ejemplo:
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Para buscar más de un equipo, escriba varios nombres de equipos encerrados entre comillas y separados por comas, como por ejemplo de la siguiente manera:
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Si necesita buscar en un grupo completo en lugar de en un solo equipo, cambie el parámetro -Computers a -Pools, quite el nombre del equipo y reemplázalo por el grupo o grupos de servidores entre comillas separados por comas.
    
    Por ejemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Al usar los comandos de búsqueda, los grupos de servidores pueden ser cualquier grupo de servidores de la implementación, como grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de chat persistente u otros que se definen como un grupo de servidores en la implementación.
    
    Por ejemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Para ejecutar una búsqueda utilizando los parámetros de hora

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. De forma predeterminada, la hora de inicio de los parámetros específicos de tiempo de una búsqueda es 25 minutos antes de cinco minutos después del momento en que inicia la búsqueda. En otras palabras, si buscamos a las 4:00:00 PM, la hora de inicio de la búsqueda se mostrará de 3:35:00 PM a 4:05:00 PM. Si necesita buscar 60 minutos o 3 horas antes de la hora actual, use el parámetro -StartTime y establezca la cadena de fecha y hora para indicar la hora en la que desea que se inicie la búsqueda. 
    
    Por ejemplo, si usa -StartTime y -EndTime para definir un intervalo de fechas y horas, puede definir una búsqueda entre las 8 a. m. y las 9 a. m. del 11/20/2012 en el grupo de servidores. Puede definir la ruta de salida para que escriba los resultados en un archivo llamado c:\logfile.txt de la manera siguiente:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La cadena de hora y fecha que especifique puede ser "fecha y hora" o "fecha de hora". " El comando analizará la cadena y usará los valores adecuados para la fecha y hora y la configuración regional y cultural en el equipo desde el que se ejecuta el cmdlet. 
  
3. Si desea recuperar registros a partir de las 11:00:00 a.m. del 11/20/2012, defina -StartTime. El intervalo de tiempo predeterminado para la búsqueda es de 30 minutos a menos que defina un -EndTime específico. La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.
    
Por ejemplo:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Para realizar una búsqueda de registros en un período de tiempo específico, defina -StartTime y -EndTime. Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net. 
    
Por ejemplo:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de coincidencia

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Para ejecutar un comando para reunir seguimientos de determinados componentes, escriba lo siguiente:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Por ejemplo:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.
    
3. Para limitar la búsqueda con los mismos componentes al grupo de servidores front-end denominado pool01.contoso.net, escriba:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos. Puede cambiar este comportamiento especificando el **parámetro -MatchAll.** Para ello, escriba lo siguiente:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder utilizando New-CsClsConfiguration para crear una nueva configuración o modificando una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la serie de registros que se buscarán, utilice el parámetro SkipNetworkLogs de la siguiente manera:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Leer registros de captura desde el servicio de registro centralizado

Se da cuenta de la ventaja real del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema notificado. Hay varias formas de leer el archivo. El archivo de salida está en un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que le permita abrir y leer un archivo de texto. Para archivos más grandes y problemas más complejos, podría usar una herramienta como Snooper.exe diseñada para leer y analizar el resultado del registro desde el servicio de registro centralizado. Snooper se incluye con las herramientas de depuración que están disponibles como descarga independiente. Puede descargar las herramientas de depuración aquí: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) . Al instalar las herramientas de depuración, no se crean los recortes y los elementos de menú. Después de instalar las herramientas de depuración, abra el Explorador de Windows, una ventana de línea de comandos o el Shell de administración de Skype Empresarial Server y vaya al directorio (ubicación predeterminada) C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración. Haga doble clic Snooper.exe o escriba Snooper.exe y, a continuación, presione ENTRAR si usa la línea de comandos o Skype Empresarial Server Shell de administración.
  
> [!IMPORTANT]
> La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas. La solución de problemas y los procesos relacionados con esta son un tema muy complejo. Para obtener más información sobre cómo solucionar problemas básicos y solucionar problemas de cargas de trabajo específicas, consulte el libro del Kit de recursos de Microsoft Lync Server 2010 en [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) . Los procesos y procedimientos aún se aplican a Skype Empresarial Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Para abrir un archivo de registro en Snooper:

1. Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos. 
    
2. Después de instalar las herramientas de depuración (LyncDebugTools.msi), cambie el directorio a la ubicación de Snooper.exe mediante Windows o desde la línea de comandos. De forma predeterminada, las herramientas de depuración se encuentran en C:\Program Files\Skype Empresarial Server 2015\Debugging Tools. Haga doble clic en Snooper.exe o ejecútelo.
    
3. Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.
    
4. Los mensajes de seguimiento **del** archivo de registro se muestran en la **pestaña** Seguimiento. Haga clic en **la pestaña** Mensajes para ver el contenido del mensaje de los seguimientos recopilados.
    
### <a name="to-display-a-call-flow-diagram"></a>Para mostrar un diagrama de flujo de llamada:

1. Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.
    
2. Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.
    
3. Haga clic en **Flujo de llamada**.
    
> [!NOTE]
> Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamadas, el diagrama no aparecerá y aparecerá un mensaje de estado en la parte inferior de Snooper que indica "Este mensaje no es apto para callfow". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada. 
  
4. Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.
    
5. Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.
