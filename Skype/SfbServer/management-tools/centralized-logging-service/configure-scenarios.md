---
title: Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumen: Aprenda a crear, modificar y quitar escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816599"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear, modificar y quitar escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.
  
Los escenarios definen el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores usar en el servicio de registro centralizado. Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia). Al configurar un escenario, puede agrupar a todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto. Si encuentra que un escenario debe modificarse para satisfacer sus necesidades de registro y solución de problemas, las herramientas de depuración de Skype empresarial Server 2015 le proporcionan un módulo de Windows PowerShell denominado ClsScenarioEdit. psm1 que contiene una función namedEdit-CsClsScenario. La finalidad del módulo es editar las propiedades del escenario en cuestión. En este tema se muestran ejemplos del funcionamiento de este módulo. Descargue las [herramientas de depuración](https://go.microsoft.com/fwlink/p/?LinkId=285257) de Skype empresarial Server 2015 antes de continuar.
  
> [!IMPORTANT]
> Para cualquier ámbito determinado (sitio, global, grupo o equipo), puede ejecutar un máximo de dos escenarios en cualquier momento. Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell y [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Mediante Windows PowerShell y [set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), puede cambiar dinámicamente qué escenarios se están ejecutando. Puede modificar qué escenarios se ejecutan durante una sesión de registro para ajustar o refinar los datos que está recopilando y de qué proveedores. 
  
Para ejecutar las funciones de los servicios de registro centralizado mediante el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contiene alguno de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet, incluidos los roles RBAC que haya creado usted mismo, ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o el símbolo del sistema de Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir un escenario, modificarlo, recuperar los escenarios en ejecución, quitar un escenario y especificar qué contiene un escenario a fin de optimizar la solución de problemas. Puede usar el shell de administración de Skype empresarial Server para emitir comandos de Windows PowerShell. Al usar Windows PowerShell, puede definir nuevos escenarios para usarlos en sus sesiones de registro.
  
Como se ha introducido en el [servicio de registro centralizado en Skype empresarial 2015](centralized-logging-service.md), los elementos de un escenario son:
  
- **Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que usted elige para indicar OCSLogger de qué debe recopilar los registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor de los que el servicio de registro centralizado puede recopilar registros. Para obtener más información sobre la configuración de proveedores, consulte [Configurar proveedores para el servicio de registro centralizado en Skype empresarial Server 2015](configure-providers.md).
    
- **Identidad** El parámetro-Identity establece el ámbito y el nombre del escenario. Por ejemplo, podría establecer un ámbito de "global" e identificar el escenario con "LyssServiceScenario". Al combinar los dos, se define la identidad (por ejemplo, "global/LyssServiceScenario").
    
    De manera opcional, puede usar los parámetros-Name y-Parent. El parámetro name se define para identificar el escenario de forma exclusiva. Si usa Name, también debe usar Parent para agregar el escenario a global o a sitio. 
    
    > [!IMPORTANT]
    > Si usa los parámetros Name y Parent, no puede usar el parámetro **-Identity** .
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con el cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) y defina el nombre del escenario (es decir, un nombre de identificación único). Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato ASCII basado en el formato de archivo de registro de IIS). Luego, defina Level y Flags tal como se definen en este tema los niveles de registro y las marcas, respectivamente.
    
    Para este escenario de ejemplo, utilizaremos LyssProvider como variable de ejemplo del proveedor.
    
    Para crear un escenario con las opciones especificadas, escriba:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Por ejemplo:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    El formato alternativo con-Name y-Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con varios proveedores por medio del cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Sin embargo, no está limitado a un número determinado de proveedores. En este ejemplo, suponga que hemos creado tres proveedores y desea asignar los tres al escenario que está definiendo. Los nombres de variable de proveedor son LyssProvider, ABServerProvider y SIPStackProvider. Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un shell de administración de Skype empresarial Server o en el símbolo del sistema de Windows PowerShell:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Como se sabe en Windows PowerShell, la Convención para crear una tabla hash de valores mediante `@{<variable>=<value1>, <value2>, <value>…}` assplatting es conocida. Para obtener más información sobre splatting en Windows PowerShell [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760), consulte. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar un escenario existente con el cmdlet Set-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que están en ejecución, la sesión de registro actual dejará de usar el escenario que se haya quitado y empezará a usar el escenario nuevo. Pero, la información de registro que se capturó con el escenario quitado se mantendrá en los registros capturados. Para definir un escenario nuevo, haga lo siguiente (es decir, suponiendo que se agregue un proveedor ya definido denominado "S4Provider"):
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Por ejemplo:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para quitar un escenario existente con el cmdlet Remove-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Si desea quitar un escenario que se definió previamente, escriba lo siguiente:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Por ejemplo, para quitar el escenario definido site:Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsScenarioEdit.psm1

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
    > [!IMPORTANT]
    > El módulo CClsScenarioEdit.psm1 se proporciona como una descarga web aparte. El módulo es parte de las herramientas de depuración de Skype empresarial Server 2015. De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración. 
  
2. En Windows PowerShell, escriba:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > La carga correcta del módulo le vuelve al símbolo del sistema de Windows PowerShell. Para confirmar que el módulo está cargado y que editar-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`. Tendría que ver una muestra general de la sintaxis de EditCsClsScenario. 
  
3. Para descargar los módulos, escriba:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > La descarga correcta del módulo te vuelve al símbolo del sistema de Windows PowerShell. Para confirmar que se ha descargado el módulo, `Get-Help Edit-CsClsScenario`escriba. Windows PowerShell intentará ubicar la ayuda para el cmdlet y fallar. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. En Windows PowerShell, escriba:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > La carga correcta del módulo le vuelve al símbolo del sistema de Windows PowerShell. Para confirmar que el módulo está cargado y que editar-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`. Tendría que ver una muestra general de la sintaxis de EditCsClsScenario. 
  
3. Para quitar un proveedor del escenario AlwaysOn, escriba:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Por ejemplo:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   La colocación posicional de los valores de parámetro solo se aplica a-Scenario y-Provider. Es necesario definir explícitamente todos los demás parámetros.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para agregar un proveedor a un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para agregar un proveedor al escenario AlwaysOn, escriba:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Por ejemplo:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -LogLevel puede ser de tipo grave, error, warning, info, verbose, Debug o ALL. -Las marcas pueden ser cualquiera de las marcas que admite el proveedor, como TF_COMPONENT, TF_DIAG. -LAS marcas también pueden ser de valor.
    
   El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, escriba:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
