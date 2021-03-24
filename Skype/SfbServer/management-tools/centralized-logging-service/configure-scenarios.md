---
title: Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Summary: Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.'
ms.openlocfilehash: 6ec6764ce3717f38fead9e88c570895f1676310f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098846"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo crear, modificar y quitar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015.
  
Los escenarios definen el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores usar en el servicio de registro centralizado. Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia). Al configurar un escenario, puede agrupar todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto. Si encuentra que es necesario modificar un escenario para satisfacer sus necesidades de solución de problemas y registro, las herramientas de depuración de Skype Empresarial Server 2015 le proporcionan un módulo de Windows PowerShell denominado ClsScenarioEdit.psm1 que contiene una función denominadaEdit-CsClsScenario. El propósito del módulo es editar las propiedades del escenario en cuestión. En este tema se muestran ejemplos del funcionamiento del módulo. Descargue las herramientas de depuración de Skype Empresarial Server 2015 antes [de](https://go.microsoft.com/fwlink/p/?LinkId=285257) continuar.
  
> [!IMPORTANT]
> Para cualquier ámbito determinado (sitio, global, grupo o equipo), puede ejecutar un máximo de dos escenarios en un momento dado. Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell [y Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps). Al usar Windows PowerShell [y Set-CsClsScenario,](/powershell/module/skype/set-csclsscenario?view=skype-ps)puede cambiar dinámicamente los escenarios que se están ejecutando. Puede modificar los escenarios que se ejecutan durante una sesión de registro para ajustar o refinar los datos que está recopilando y de qué proveedores. 
  
Para ejecutar las funciones del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC) o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles RBAC a los que se asignó este cmdlet, incluidos los roles RBAC personalizados que haya creado usted mismo, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o el símbolo del sistema Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir un escenario, modificar un escenario, recuperar qué escenarios se están ejecutando, quitar un escenario y especificar qué contiene un escenario para optimizar la solución de problemas. Puede usar el Shell de administración de Skype Empresarial Server para emitir Windows PowerShell comandos. Al usar Windows PowerShell, puede definir nuevos escenarios para su uso en las sesiones de registro.
  
Como se introdujo en el Servicio de registro centralizado [en Skype Empresarial 2015,](centralized-logging-service.md)los elementos de un escenario son:
  
- **Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que elige para decir a OCSLogger de qué debe recopilar registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor de los que el servicio de registro centralizado puede recopilar registros. Para obtener más información sobre la configuración de proveedores, vea [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).
    
- **Identidad** El parámetro -Identity establece el ámbito y el nombre del escenario. Por ejemplo, podría establecer un ámbito de "global" e identificar el escenario con "LyssServiceScenario". Al combinar los dos, se define la identidad (por ejemplo, "global/LyssServiceScenario").
    
    Opcionalmente, puede usar los parámetros -Name y -Parent. El parámetro Name se define para identificar de forma única el escenario. Si usa Name, también debe usar Parent para agregar el escenario a un sitio o global. 
    
    > [!IMPORTANT]
    > Si usa los parámetros Name y Parent, no puede usar el **parámetro -Identity.**
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con el cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) y defina el nombre del escenario (es decir, un nombre de identificación único). Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato basado en el formato de archivo de registro de IIS). A continuación, defina Level y Flags tal como se definen en este tema los niveles de registro y las etiquetas, respectivamente.
    
    Para este escenario de muestra, utilizaremos LyssProvider como variable del proveedor.
    
    Para crear un escenario con las opciones especificadas, escriba:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Por ejemplo:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    El formato alternativo mediante -Name y -Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con varios proveedores con el cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Sin embargo, el número de proveedores no está limitado. Para este ejemplo, supongamos que ha creado tres proveedores y que desea asignarlos al escenario que está definiendo. Los nombres de la variable "provider" son LyssProvider, ABServerProvider y SIPStackProvider. Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un Shell de administración de Skype Empresarial Server o Windows PowerShell símbolo del sistema:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Como se conoce en Windows PowerShell, la convención para crear una tabla hash de valores mediante se conoce  `@{<variable>=<value1>, <value2>, <value>…}` como "assplatting". Para obtener más información acerca de la Windows PowerShell, vea [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar un escenario existente con el cmdlet Set-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que se están ejecutándose, la sesión de registro actual dejará de usar el escenario que se haya quitado y comenzará a usar el escenario nuevo. No obstante, la información de registro que se capturó con el escenario que se haya quitado se mantendrá en los registros capturados. Para definir un nuevo escenario, haga lo siguiente (es decir, suponiendo que se agrega un proveedor ya definido denominado "S4Provider"):
    
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

    Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, el código sería:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para quitar un escenario existente con el cmdlet Remove-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Si desea quitar un escenario que se definió previamente, escriba lo siguiente:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Por ejemplo, para reemplazar el escenario definido con site:Redmond/LyssServiceScenario, el código sería:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsScenarioEdit.psm1

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
    > [!IMPORTANT]
    > El módulo ClsScenarioEdit.psm1 se proporciona como una descarga web independiente. El módulo forma parte de las herramientas de depuración de Skype Empresarial Server 2015. De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Program Files\Skype for Business Server 2015\Debugging Tools. 
  
2. En el Windows PowerShell, escriba:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > La carga correcta del módulo le devuelve al Windows PowerShell de comandos. Para confirmar que el módulo está cargado y que Edit-CsClsScenario está disponible, escriba  `Get-Help Edit-CsClsScenario` . Debería ver una muestra general de la sintaxis de EditCsClsScenario. 
  
3. Para descargar los módulos, escriba:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > La descarga correcta del módulo le devuelve al Windows PowerShell de comandos. Para confirmar que el módulo está descargado, escriba  `Get-Help Edit-CsClsScenario` . Windows PowerShell buscará la ayuda del cmdlet y producirá un error. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. En el Windows PowerShell, escriba:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > La carga correcta del módulo le devuelve al Windows PowerShell de comandos. Para confirmar que el módulo está cargado y que Edit-CsClsScenario está disponible, escriba  `Get-Help Edit-CsClsScenario` . Debería ver una muestra general de la sintaxis de EditCsClsScenario. 
  
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

   La colocación posicional de los valores de parámetro solo se aplica a -Scenario y -Provider. Todos los demás parámetros se deben definir explícitamente.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para agregar un proveedor a un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Para agregar un proveedor al escenario AlwaysOn, escriba:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Por ejemplo:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel puede ser del tipo Fatal, Error, Warning, Info, Verbose, Debug o All. -Flags puede ser cualquiera de las marcas que admite el proveedor, como TF_COMPONENT, TF_DIAG. -Flags también puede ser de valor ALL
    
   El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, el código quedaría así:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```