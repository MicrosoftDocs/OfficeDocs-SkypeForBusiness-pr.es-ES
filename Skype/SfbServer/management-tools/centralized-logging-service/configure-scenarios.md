---
title: Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumen: Obtenga información sobre cómo crear, modificar y eliminar los escenarios para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 453c9c593e53dca186b09e1ba835bc8f94bb7112
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217680"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo crear, modificar y eliminar los escenarios para el servicio de registro centralizado en Skype para Business Server 2015.
  
Escenarios de definición el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores para usar en el servicio de registro centralizado. Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia). Al configurar un escenario, puede agrupar a todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto. Si observa que debe modificarse para satisfacer la solución de problemas y registro de las necesidades de un escenario, el Skype para las herramientas de depuración de Business Server 2015 proporciona un módulo de Windows PowerShell denominado ClsScenarioEdit.psm1 que contiene una función namedEdit-CsClsScenario. La finalidad del módulo es editar las propiedades del escenario en cuestión. En este tema se muestran ejemplos del funcionamiento de este módulo. Descargue el Skype para [Herramientas de depuración](https://go.microsoft.com/fwlink/p/?LinkId=285257) de Business Server 2015 antes continuar cualquiera.
  
> [!IMPORTANT]
> Para cualquier ese ámbito: global, sitio, grupo o equipo, puede ejecutar un máximo de dos escenarios en un momento dado. Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell y [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Mediante el uso de Windows PowerShell y [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), puede cambiar dinámicamente qué escenarios se están ejecutando. Puede modificar qué escenarios se ejecutan durante una sesión de registro para ajustar o restringir los datos que se va a recopilar y de los proveedores. 
  
Para ejecutar las funciones de servicio de registro centralizado mediante el uso de la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos. Para devolver una lista de todos los el RBAC roles que se ha asignado este cmdlet, incluidos los roles RBAC personalizados que haya creado, ejecutan el siguiente comando desde el Skype para Business Server Management Shell o el símbolo del sistema de Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir un escenario, modificarlo, recuperar los escenarios en ejecución, quitar un escenario y especificar qué contiene un escenario a fin de optimizar la solución de problemas. Puede usar el Skype para Shell de administración de servidor empresarial para emitir los comandos de Windows PowerShell. Cuando se usa Windows PowerShell, puede definir nuevos escenarios para su uso en las sesiones de registro.
  
Como se comentó en [Servicio de registro centralizado en Skype para profesionales de 2015](centralized-logging-service.md), los elementos de un escenario son:
  
- **Proveedores de** Si está familiarizado con OCSLogger, los proveedores son los componentes que elija para indicar a OCSLogger el motor de seguimiento de qué debe recopilar los registros de. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor que el servicio de registro centralizado puede recopilar los registros de. Para obtener información detallada sobre la configuración de proveedores, vea [Configurar proveedores de servicio de registro centralizado en Skype para Business Server 2015](configure-providers.md).
    
- **Identidad** El parámetro-Identity establece el ámbito y el nombre del escenario. Por ejemplo, podría establecer un ámbito de "global" e identificar el escenario con "LyssServiceScenario". Cuando se combinan las dos, definir la identidad (por ejemplo, "global/LyssServiceScenario").
    
    De forma opcional, puede usar los parámetros - nombre y - primario. Definir el parámetro Name para identificar de forma exclusiva el escenario. Si utiliza un nombre, también debe usar primario para agregar el escenario alguna global o sitio. 
    
    > [!IMPORTANT]
    > Si usa los parámetros Name y Parent, no se puede usar el **-Identity** parámetro.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con el cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) y defina el nombre del escenario (es decir, un nombre de identificación único). Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato ASCII basado en el formato de archivo de registro de IIS). Luego, defina Level y Flags tal como se definen en este tema los niveles de registro y las marcas, respectivamente.
    
    Para este escenario de ejemplo, utilizaremos LyssProvider como variable de ejemplo del proveedor.
    
    Para crear un escenario con las opciones especificadas, escriba:
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Por ejemplo:
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    El formato alternativo utilizando - Name y - Parent:
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para crear un escenario con varios proveedores por medio del cmdlet New-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Sin embargo, no está limitado a un número determinado de proveedores. En este ejemplo, se supone que hemos creado tres proveedores, y que desea asignar las tres para el escenario que se está definiendo. Los nombres de variable de proveedor son LyssProvider, ABServerProvider y SIPStackProvider. Para definir y asignar a varios proveedores para un escenario, escriba lo siguiente en un Skype para símbolo del Shell de administración de servidor empresarial o Windows PowerShell:
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Como se conoce en Windows PowerShell, la convención para la creación de una tabla hash de los valores con `@{<variable>=<value1>, <value2>, <value>…}` se conoce assplatting. Para obtener información detallada acerca de splatting en Windows PowerShell, consulte [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760). 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar un escenario existente con el cmdlet Set-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que están en ejecución, la sesión de registro actual dejará de usar el escenario que se haya quitado y empezará a usar el escenario nuevo. Pero, la información de registro que se capturó con el escenario quitado se mantendrá en los registros capturados. Para definir un nuevo escenario, haga lo siguiente (es decir, si la adición de un proveedor ya definido denominado "S4Provider"):
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Por ejemplo:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para quitar un escenario existente con el cmdlet Remove-CsClsScenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Si desea quitar un escenario que se definió previamente, escriba lo siguiente:
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Por ejemplo, para quitar el escenario definido site:Redmond/LyssServiceScenario:
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsScenarioEdit.psm1

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
    > [!IMPORTANT]
    > El módulo CClsScenarioEdit.psm1 se proporciona como una descarga web aparte. El módulo es parte de la Skype para las herramientas de depuración de Business Server 2015. De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración. 
  
2. En Windows PowerShell, escriba:
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Carga correcta del módulo vuelve a la línea de comandos de Windows PowerShell. Para confirmar que el módulo se carga y que Edit-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`. Tendría que ver una muestra general de la sintaxis de EditCsClsScenario. 
  
3. Para descargar los módulos, escriba:
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > Correcta descarga de las devoluciones de módulo, en el símbolo del sistema de Windows PowerShell. Para confirmar que se descarga el módulo, escriba `Get-Help Edit-CsClsScenario`. Windows PowerShell se intentará buscar la ayuda para el cmdlet y producirá un error. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. En Windows PowerShell, escriba:
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Carga correcta del módulo vuelve a la línea de comandos de Windows PowerShell. Para confirmar que el módulo se carga y que Edit-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`. Tendría que ver una muestra general de la sintaxis de EditCsClsScenario. 
  
3. Para quitar un proveedor del escenario AlwaysOn, escriba:
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Por ejemplo:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   La colocación de posición de los valores de parámetro sólo aplica a - escenario y - proveedor. Es necesario definir explícitamente todos los demás parámetros.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para agregar un proveedor a un escenario con el módulo Edit-ClsController

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para agregar un proveedor al escenario AlwaysOn, escriba:
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Por ejemplo:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Loglevel - puede ser del tipo de error grave, Error, advertencia, información, detallado, depurar o todos. -Flags pueden ser cualquiera de los indicadores que admite el proveedor, como TF_COMPONENT, TF_DIAG. -Flags también pueden ser de valor todos
    
   El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, escriba:
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
