---
title: Configuración de escenarios para el servicio de registro centralizado
TOCTitle: Configuración de escenarios para el servicio de registro centralizado
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49889220
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de escenarios para el servicio de registro centralizado

 

_**Última modificación del tema:** 2016-12-08_

Los escenarios definen el ámbito (que puede ser global o de un sitio, un grupo o un equipo) y los proveedores que se utilizarán en el Servicio de registro centralizado. Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia). Al configurar un escenario, puede agrupar a todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto. Si cree que es necesario modificar un escenario para satisfacer sus necesidades de solución de problemas y de inicio de sesión, las herramientas de depuración de Lync Server 2013 le proporcionan un módulo de Windows PowerShell llamado *ClsController.psm1* que contiene la función *Edit-CsClsScenario*. La finalidad del módulo es editar las propiedades del escenario en cuestión. En este tema se muestran ejemplos del funcionamiento de este módulo. Las herramientas de depuración de Lync Server 2013 se pueden descargar en el siguiente vínculo: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

> [!IMPORTANT]  
> Para cualquiera de los ámbitos —global, de sitio, de grupo o de equipo—, puede ejecutar un máximo de dos escenarios al mismo tiempo. Para ver qué escenarios están en ejecución, utilice Windows PowerShell y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</a>. Con Windows PowerShell y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</a>, puede cambiar de forma dinámica los escenarios que están en ejecución: puede modificar los escenarios que se ejecutan durante una sesión de registro o bien ajustar o restringir los datos que se recopilan y sus proveedores.



Para ejecutar las funciones del Servicio de registro centralizado con el Shell de administración de Lync Server, es necesario que pertenezca a los grupos de seguridad de control de acceso basado en roles (RBAC) CsServerAdministrator o CsAdministrator, o bien a un rol RBAC personalizado que contenga alguno de estos dos grupos. Para obtener una lista de todos los roles RBAC a los que este cmdlet se asignó, incluidos los roles RBAC personalizados creados por usted, ejecute este comando desde el símbolo del sistema de Windows PowerShell o el Shell de administración de Lync Server:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

De aquí en adelante nos centraremos en cómo definir, modificar y quitar un escenario, cómo recuperar los escenarios en ejecución y cómo especificar el contenido de un escenario para optimizar la solución de problemas. Los comandos del Servicio de registro centralizado se pueden emitir de dos maneras: con CLSController.exe, que se encuentra, de forma predeterminada, en el directorio C:\\Archivos de programa\\Archivos comunes\\Microsoft Lync Server 2013\\CLSAgent, o bien con el Shell de administración de Lync Server para emitir comandos de Windows PowerShell. La diferencia principal es que al utilizar CLSController.exe en la línea de comandos, hay disponible un conjunto limitado de escenarios, mientras que con Windows PowerShell se pueden definir escenarios nuevos para usarlos en las sesiones de registro.

Como se comentó en [Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md), un escenario consta de los elementos siguientes:

  - **Proveedores**   Si está familiarizado con OCSLogger, los proveedores son los componentes que elige para decirle a OCSLogger desde dónde debe recopilar registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de rol del servidor desde los que el Servicio de registro centralizado puede recopilar registros. Para más información sobre la configuración de los proveedores, vea [Configurar proveedores para el servicio de registro centralizado](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identidad**   El parámetro –Identity define el ámbito y el nombre del escenario. Por ejemplo, puede establecer un ámbito “global” e identificar el escenario como “LyssServiceScenario”. Cuando se combinan ambos, se define la identidad, que en este caso sería “global/LyssServiceScenario”.
    
    Si lo desea, puede usar los parámetros –Name y –Parent. Si utiliza el parámetro Name, que únicamente sirve para identificar el escenario, también deberá usar el parámetro Parent para agregar el escenario a "global" o a "site".
    
    > [!IMPORTANT]  
    > Si usa los parámetros Name y Parent, no puede usar el parámetro <strong>–Identity</strong>.
    


## Para crear un escenario con el cmdlet New-CsClsScenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider) y defina el nombre del escenario (es decir, un nombre de identificación único). Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato basado en el formato de archivo de registro de IIS). A continuación, defina Level y Flags tal como se definen en este tema los niveles de registro y las etiquetas, respectivamente.
    
    Para este escenario de muestra, utilizaremos LyssProvider como variable del proveedor.
    
    Para crear un escenario con las opciones especificadas, escriba:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Por ejemplo:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Formato alternativo en el que se usan –Name y –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

## Para crear un escenario con varios proveedores con el cmdlet New-CsClsScenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Por cada ámbito puede haber un máximo de dos escenarios. Sin embargo, el número de proveedores no está limitado. Para este ejemplo, supongamos que ha creado tres proveedores y que desea asignarlos al escenario que está definiendo. Los nombres de la variable "provider" son LyssProvider, ABServerProvider y SIPStackProvider. Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un símbolo del sistema de Windows PowerShell o el Shell de administración de Lync Server:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    

    > [!NOTE]
    > Al igual que en Windows PowerShell, la convención de crear una tabla hash de valores con <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> se conoce en inglés como <EM>splatting</EM>. Para más información sobre este proceso en Windows PowerShell, consulte <A href="http://go.microsoft.com/fwlink/?linkid=267760%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=267760&amp;clcid=0xC0A</A>.



## Para modificar un escenario existente con el cmdlet Set-CsClsScenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que se están ejecutándose, la sesión de registro actual dejará de usar el escenario que se haya quitado y comenzará a usar el escenario nuevo. No obstante, la información de registro que se capturó con el escenario que se haya quitado se mantendrá en los registros capturados. Para definir un escenario nuevo, introduzca lo siguiente (asumiendo que se definió un proveedor con el nombre “S4Provider”):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Por ejemplo:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, el código sería:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

## Para quitar un escenario existente con el cmdlet Remove-CsClsScenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Si desea quitar un escenario que se definió previamente, escriba lo siguiente:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Por ejemplo, para reemplazar el escenario definido con site:Redmond/LyssServiceScenario, el código sería:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.

## Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsController.psm1

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.
    
    > [!IMPORTANT]  
    > El módulo ClsController.psm1, que forma parte de las herramientas de depuración de Lync Server 2013, se proporciona como una descarga web aparte. De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de programa\Lync Server 2013\Herramientas de depuración.
    


2.  En Windows PowerShell, escriba:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    > [!TIP]  
    > Si el módulo se carga correctamente, se le llevará de nuevo al símbolo del sistema de Windows PowerShell. Para confirmar que el módulo se cargó y que Edit-CsClsScenario está disponible, escriba <code>Get-Help Edit-CsClsScenario</code>. Debería ver una muestra general de la sintaxis de EditCsClsScenario.
    


3.  Para descargar los módulos, escriba:
    
        Remove-Module ClsController
    
    > [!TIP]  
    > Si el módulo se descarga correctamente, se le llevará de nuevo al símbolo del sistema de Windows PowerShell. Para confirmar que el módulo se descargó, escriba <code>Get-Help Edit-CsClsScenario</code>. Windows PowerShell tratará de localizar la ayuda sobre el cmdlet y se suspenderá.
    


## Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para quitar un proveedor del escenario AlwaysOn, escriba:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Por ejemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    La colocación posicional de los valores de parámetro solo se aplica a –Scenario y –Provider. Todos los demás parámetros se deben definir explícitamente.

## Para agregar un proveedor a un escenario con el módulo Edit-ClsController

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para agregar un proveedor al escenario AlwaysOn, escriba:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Por ejemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    Los únicos tipos posibles de nivel de registro son: Fatal, Error, Warning, Info, Verbose, Debug o All. –Flags pueden ser cualquiera de las marcas que el proveedor admita, como TF\_COMPONENT, TF\_DIAG, o bien pueden contener el valor ALL.
    
    El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, el código quedaría así:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

