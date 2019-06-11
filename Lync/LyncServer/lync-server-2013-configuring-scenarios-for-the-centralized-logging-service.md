---
title: 'Lync Server 2013: configuración de escenarios para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Configuración de escenarios para el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Los escenarios definen el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores usar en el servicio de registro centralizado. Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia). Al configurar un escenario, puede agrupar a todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto. Si encuentra que un escenario debe modificarse para satisfacer sus necesidades de solución de problemas y registro, las herramientas de depuración de Lync Server 2013 le proporcionan un módulo de Windows PowerShell denominado *ClsController. psm1* que contiene una función denominada *Edit-CsClsScenario *. La finalidad del módulo es editar las propiedades del escenario en cuestión. En este tema se muestran ejemplos del funcionamiento de este módulo. Las herramientas de depuración de Lync Server 2013 se descargan desde el siguiente vínculo:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Para cualquier ámbito determinado (sitio, global, grupo o equipo), puede ejecutar un máximo de dos escenarios en cualquier momento. Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell y <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>. Mediante Windows PowerShell y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">set-CsClsScenario</A>, puede cambiar dinámicamente qué escenarios se están ejecutando. Puede modificar qué escenarios se ejecutan durante una sesión de registro para ajustar o refinar los datos que está recopilando y de qué proveedores.



</div>

Para ejecutar las funciones de los servicios de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contenga cualquiera de los dos de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet, incluidos los roles RBAC que haya creado usted mismo, ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto de este tema se centra en cómo definir un escenario, modificarlo, recuperar los escenarios en ejecución, quitar un escenario y especificar qué contiene un escenario a fin de optimizar la solución de problemas. Hay dos formas de emitir comandos de servicio de registro centralizados. Puede usar el CLSController. exe, que se encuentra de forma predeterminada, en el directorio C:\\archivos de\\programa archivos\\comunes Microsoft Lync Server\\2013 CLSAgent. O bien, puede usar el shell de administración de Lync Server para emitir comandos de Windows PowerShell. La diferencia importante es que cuando usa CLSController. exe en la línea de comandos, hay una selección finita de escenarios disponibles. Al usar Windows PowerShell, puede definir nuevos escenarios para usarlos en sus sesiones de registro.

Como se introdujo en [información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), los elementos de un escenario son:

  - **Proveedores**   si está familiarizado con OCSLogger, los proveedores son los componentes que usted elige para indicar OCSLogger de qué debe recopilar los registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor de los que el servicio de registro centralizado puede recopilar registros. Para más información sobre la configuración de proveedores, consulte [configuración de proveedores para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   el parámetro-Identity establece el ámbito y el nombre del escenario. Por ejemplo, puede establecer un ámbito "global" e identificar el escenario como "LyssServiceScenario". Cuando se combinan ambos, se define la identidad, que en este caso sería "global/LyssServiceScenario".
    
    Si lo desea, puede usar los parámetros –Name y –Parent. Si utiliza el parámetro Name, que únicamente sirve para identificar el escenario, también tendrá que usar el parámetro Parent para agregar el escenario de forma global o en el sitio.
    
    <div>
    

    > [!IMPORTANT]  
    > Si usa los parámetros Name y Parent, no puede usar el parámetro <STRONG>–Identity</STRONG>.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con el cmdlet New-CsClsScenario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) y defina el nombre del escenario (es decir, un nombre de identificación único). Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato ASCII basado en el formato de archivo de registro de IIS). Luego, defina Level y Flags tal como se definen en este tema los niveles de registro y las marcas, respectivamente.
    
    Para este escenario de ejemplo, utilizaremos LyssProvider como variable de ejemplo del proveedor.
    
    Para crear un escenario con las opciones especificadas, escriba:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Por ejemplo:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Formato alternativo en el que se usan –Name y –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con varios proveedores por medio del cmdlet New-CsClsScenario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Por cada ámbito puede haber un máximo de dos escenarios. Sin embargo, no está limitado a un número determinado de proveedores. En este ejemplo, suponga que hemos creado tres proveedores y desea asignar los tres al escenario que está definiendo. Los nombres de variable de proveedor son LyssProvider, ABServerProvider y SIPStackProvider. Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un shell de administración de Lync Server o en el símbolo del sistema de Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Como se sabe en Windows PowerShell, la Convención para crear una tabla hash de valores usando <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> se conoce como <EM>splatting</EM>. Para obtener más información sobre splatting en Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>, consulte.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar un escenario existente con el cmdlet Set-CsClsScenario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que están en ejecución, la sesión de registro actual dejará de usar el escenario que se haya quitado y empezará a usar el escenario nuevo. Pero, la información de registro que se capturó con el escenario quitado se mantendrá en los registros capturados. Para definir un escenario nuevo, haga lo siguiente (suponiendo que se agregó un proveedor ya definido con el nombre "S4Provider"):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Por ejemplo:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para quitar un escenario existente con el cmdlet Remove-CsClsScenario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Si desea quitar un escenario que se definió previamente, escriba lo siguiente:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Por ejemplo, para quitar el escenario definido site:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsController. psm1

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.
    
    <div>
    

    > [!IMPORTANT]  
    > El módulo ClsController. psm1 se proporciona como una descarga web independiente. El módulo es parte de las herramientas de depuración de Lync Server 2013. De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de Files\Lync Server 2013 \ depuración.

    
    </div>

2.  En Windows PowerShell, escriba:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > La carga correcta del módulo le vuelve al símbolo del sistema de Windows PowerShell. Para confirmar que el módulo está cargado y que editar-CsClsScenario está disponible, escriba <CODE>Get-Help Edit-CsClsScenario</CODE>. Tendría que ver una muestra general de la sintaxis de EditCsClsScenario.

    
    </div>

3.  Para descargar los módulos, escriba:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > La descarga correcta del módulo te vuelve al símbolo del sistema de Windows PowerShell. Para confirmar que se ha descargado el módulo, <CODE>Get-Help Edit-CsClsScenario</CODE>escriba. Windows PowerShell intentará ubicar la ayuda para el cmdlet y fallar.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para quitar un proveedor del escenario AlwaysOn, escriba:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Por ejemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    La colocación posicional de los valores de parámetro solo se aplica a –Scenario y –Provider. Es necesario definir explícitamente todos los demás parámetros.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para agregar un proveedor a un escenario con el módulo Edit-ClsController

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para agregar un proveedor al escenario AlwaysOn, escriba:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Por ejemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel puede ser de tipo grave, error, warning, info, verbose, Debug o ALL. – Flags puede corresponder a cualquiera de las marcas admitidas por el proveedor\_, como TF\_Component, TF diag. : Los indicadores también pueden tener valor
    
    El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, escriba:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

