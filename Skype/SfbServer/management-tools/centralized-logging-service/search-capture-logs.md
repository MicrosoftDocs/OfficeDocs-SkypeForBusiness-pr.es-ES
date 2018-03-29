---
title: Buscar registros de captura creados por el servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumen: Conozca cómo buscar y leer los registros de captura de servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: ccf9827848d190179b5f942646a74947047c02c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Buscar registros de captura creados por el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a buscar y leer los registros de captura de servicio de registro centralizado en Skype para Business Server 2015.
  
Las características de búsqueda en el servicio de registro centralizado son útiles y eficaces por las siguientes razones: 
  
- Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.
    
- Sus búsquedas pueden ser inicialmente amplias y, luego, acotarse a un criterio más específico, como la hora, el componente o el equipo. Buscar en los registros de la mismos y no necesita ejecutar una sesión de registro nuevo cuando cambie el criterio de búsqueda.
    
- Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitados a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Es posible utilizar herramientas familiares, como **Snooper** o el **Bloc de notas** para leer el archivo de salida y los mensajes de seguimiento desde la implementación.
    
El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). El CLSAgent administra los registros y sus archivos caché e índice asociados. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información necesita recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController, luego, agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.
  
Después de cada búsqueda, se ejecuta el cmdlet de **Sincronización CsClsLogging** y vacía la memoria caché utilizada búsquedas (no debe confundirse con los archivos de caché mantenidos por la CLSAgent). Vaciar la memoria caché ayuda a asegurar de que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.
  
Para obtener el mayor beneficio desde el servicio de registro centralizado, es necesario una buena comprensión de cómo configurar la búsqueda para devolver sólo los mensajes de seguimiento de los registros de equipo y de grupo que son relevantes para el problema que está investigando. problemas
  
Para ejecutar las funciones de búsqueda del servicio de registro centralizado mediante el Skype para negocios de Shell de administración de servidor, debe ser miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) de control o una función personalizada de RBAC que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet en (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para el Shell de administración de servidor de negocios o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir una búsqueda para optimizar la resolución de problemas.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica mediante el servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en la implementación en el ámbito global y, luego, escriba lo siguiente en un símbolo del sistema:
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> De manera predeterminada, Search-CsClsLogging envía los resultados de la búsqueda a la consola. Si desea guardar los resultados de búsqueda en un archivo, use - OutputFilePath _ \<ruta de acceso completa del archivo de cadena\>_. Para definir el parámetro - OutputFilePath, proporcione una ruta de acceso y un nombre de archivo como parte del parámetro en un formato de cadena entre comillas (por ejemplo; C:\LogFiles\SearchOutput.txt). En este ejemplo, es preciso asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS de modificación) de archivos de la carpeta. El resultado se anexa y no se sobrescribe. Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda. 
  
Por ejemplo:
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para ejecutar una búsqueda básica en un equipo o grupo mediante el servicio de registro centralizado

1. Para limitar la búsqueda a un equipo o un grupo específico, utilice el - parámetro de equipos con el equipo definido por un nombre completo de equipo, entre comillas y separados por una coma, como sigue:
    
  ```
  Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
  ```

Por ejemplo:
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Para buscar en más de un equipo, escriba varios nombres de equipos entre comillas y separados por comas, como, por ejemplo, de la siguiente manera:
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

3. Si necesita buscar un depósito completo en lugar de un único equipo, cambiar el equipos parámetro - a - Pools, quitar el nombre del equipo y reemplazar con el grupo o los grupos de comillas separadas por comas.
    
    Por ejemplo:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Al utilizar los comandos de búsqueda, grupos pueden ser cualquier grupo de la implementación, como grupos de Front-End, pools de borde, grupos de servidores de charla persistente u otros que se definen como un grupo en la implementación.
    
    Por ejemplo:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Para ejecutar una búsqueda utilizando los parámetros de hora

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. De manera predeterminada, la hora de inicio para los parámetros específicos de hora de una búsqueda es de 25 minutos antes hasta cinco minutos después de la hora en que inició la búsqueda. En otras palabras, si la búsqueda se hace a las 16:00:00, la hora de inicio de la búsqueda se mostrará desde las 15:35:00 hasta las 16:05:00. Si necesita buscar en 60 minutos o 3 horas antes de la hora actual, utilice el parámetro - StartTime y establecer la cadena de fecha y hora para indicar el tiempo que desea iniciar la búsqueda. 
    
    Por ejemplo, mediante - StartTime y EndTime: para definir un intervalo de fecha y hora, puede definir una búsqueda entre 8 y 9 AM el 20/11/2012 en su grupo. Puede definir la ruta de salida para que escriba los resultados en un archivo llamado c:\logfile.txt de la manera siguiente:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> La cadena de fecha y hora que especifique puede ser "fecha hora" u "hora fecha". "El comando analizar la cadena y utilizar los valores apropiados para la fecha y hora de la configuración regional y la referencia cultural en el equipo que está ejecutando el cmdlet desde. 
  
3. Si desea recuperar registros a partir de 11:00:00 A.M. el 20/11/2012, defina el StartTime. El intervalo de tiempo predeterminado para la búsqueda es de 30 minutos a menos que defina un EndTime - específico. La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.
    
Por ejemplo:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Para realizar una búsqueda de registros dentro de un período específico de tiempo, defina un - StartTime y una hora de finalización. Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net. 
    
Por ejemplo:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de resultados

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para ejecutar un comando a fin de recopilar seguimientos de determinados componentes, escriba lo siguiente:
    
  ```
  Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
  ```

Por ejemplo:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.
    
3. Para limitar la búsqueda con los mismos componentes que sólo el grupo de servidores de Front-End denominada pool01.contoso.net, escriba:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos. Puede cambiar este comportamiento especificando el parámetro **- MatchAll** . Para ello, escriba lo siguiente:
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder, al utilizar New-CsClsConfiguration para crear una nueva configuración o al modificar una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la colección de registros que se buscará, utilice el parámetro SkipNetworkLogs de la siguiente manera:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Leer los registros de captura desde el servicio de registro centralizado

Obtenga los beneficios del servicio de registro centralizado real después de ejecutar la búsqueda y tiene un archivo que puede utilizar para realizar un seguimiento de un problema. Hay varias formas de leer el archivo. El archivo de salida tiene un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que permita abrir y leer un archivo de texto. Para archivos más grandes y más complejos problemas, puede utilizar una herramienta como Snooper.exe que está diseñado para leer y analizar los resultados del registro desde el servicio de registro centralizado. Snooper forma parte de las herramientas de depuración disponibles como una descarga independiente. Puede descargar las herramientas de depuración aquí: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Al instalar las herramientas de depuración, no se crean accesos directos y elementos de menú. Después de instalar las herramientas de depuración, abra el Explorador de Windows, una ventana de línea de comandos o Skype para el Shell de administración de servidor empresarial y vaya al directorio (ubicación predeterminada) C:\Program Files\Skype para herramientas de Business Server 2015\Debugging. Haga doble clic en Snooper.exe o escriba Snooper.exe y, a continuación, presione ENTRAR si utiliza la línea de comandos o Skype para el Shell de administración de servidor de empresa.
  
> [!IMPORTANT]
> La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas. La solución de problemas y los procesos relacionados con esta son un tema muy complejo. Para obtener detalles acerca de los conceptos básicos de solución de problemas y solución de problemas de cargas de trabajo específicas, consulte el libro Kit de recursos de Microsoft Lync Server 2010 en [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Los procesos y procedimientos siguen Skype para Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Para abrir un archivo de registro en Snooper

1. Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro tiene que ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos. 
    
2. Tras la instalación de las herramientas de depuración de (LyncDebugTools.msi), vaya al directorio donde se encuentra Snooper.exe con el Explorador de Windows o desde la línea de comandos. De forma predeterminada, las herramientas de depuración se encuentran en C:\Program Files\Skype para herramientas de Business Server 2015\Debugging. Haga doble clic en Snooper.exe o ejecútelo.
    
3. Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.
    
4. Se muestran los mensajes del archivo de registro de **seguimiento** en el **seguimiento** de la ficha, haga clic en la ficha **mensajes** para ver el contenido del mensaje de las trazas recopilados.
    
### <a name="to-display-a-call-flow-diagram"></a>Para mostrar un diagrama de flujo de llamada

1. Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro es preciso ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.
    
2. Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.
    
3. Haga clic en **Flujo de llamada**.
    
> [!NOTE]
> Si hace clic en una traza que no forma parte de un flujo de llamadas o de mensaje, no aparecerá en el diagrama y aparece un mensaje de estado en la parte inferior de espía que indica "este mensaje no es elegible para callfow". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada. 
  
4. Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.
    
5. Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.