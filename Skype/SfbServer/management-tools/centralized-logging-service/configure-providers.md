---
title: Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumen: Conozca cómo configurar proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: a609d7406f59702aeb906a21132eff5f861ce037
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a configurar proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.
  
Los conceptos y la configuración de los proveedores de servicio de registro centralizado es uno de los más importantes de entender. Theproviders se asignan directamente a Skype para componentes del rol de servidor Business Server en el Skype para el modelo de seguimiento Business Server. El proveedor define los componentes de un Skype para Business Server 2015 traza, el tipo de mensajes (por ejemplo, grave, error o advertencia) para recopilar y los indicadores (por ejemplo, TF_Connection o TF_Diag). Los proveedores son los componentes con trazabilidad en cada Skype para la función de servidor de Business Server. Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.
  
Para ejecutar las funciones de servicio de registro centralizado utilizando el Skype para negocios de Shell de administración de servidor, debe ser miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) de control o una función personalizada de RBAC que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones de control (RBAC) de acceso basada en funciones se ha asignado este cmdlet a (incluidos los roles RBAC personalizados que haya creado), ejecute el comando siguiente desde el Skype para el Shell de administración de servidor de negocios o el de Windows PowerShell símbolo del sistema:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y lo que contiene una definición de proveedor para optimizar la solución de problemas. Hay dos maneras de emitir comandos de servicio de registro centralizado. Puede utilizar el CLSController.exe que se encuentra de forma predeterminada, en el directorio C:\Program Files\Common Files\Skype Business Server 2015\CLSAgent. O bien, puede utilizar el Skype para negocios de Shell de administración de servidor para emitir comandos de Windows PowerShell. Mediante el uso de Windows PowerShell, puede definir nuevos proveedores para su uso en las sesiones de registro y tener un control completo sobre su creación, lo que recogen, y en qué nivel recopilar datos.
  
> [!IMPORTANT]
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos. 
  
En lugar de tener que adentrarse profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya se han definido por usted. Los escenarios proporcionados cubren la gran mayoría de los posibles problemas que se producirán. En raras ocasiones, puede que necesite crear y definir los proveedores y asignarlos a los escenarios. Se recomienda encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear escenarios y nuevos proveedores. Información sobre la creación de proveedores se encuentre aquí para familiarizarse con los escenarios de uso que los elementos de proveedor para recopilar información de seguimiento, no se proporcionan detalles sobre los propios proveedores en este momento. 
  
Introducido en el [Servicio de registro centralizado en Skype para negocios 2015](centralized-logging-service.md), los elementos clave de la definición de un proveedor para su uso en un escenario son:
  
- **Proveedores** Si está familiarizado con los OCSLogger, los proveedores son los componentes que elige decir a OCSLogger lo que el motor de seguimiento debe recopilar registros de. Los proveedores son los mismos componentes (y, muchas veces, con los mismos nombres) que los de OCSLogger. Si no está familiarizado con los OCSLogger, los proveedores son función de servidor de componentes específicos que el servicio de registro centralizado puede recopilar registros de. En el caso del servicio centralizado de registro, el CLSAgent es la parte de arquitectura centralizada de registro del servicio de que está realizando el seguimiento de los componentes que se definen en la configuración de proveedores.
    
- **Niveles de registro** OCSLogger proporciona la opción de elegir un número de niveles de detalle de los datos recopilados. Esta característica es una parte integral del servicio de registro centralizado y escenarios y se define mediante el parámetro de **tipo** . Puede elegir entre las siguientes opciones:
    
  - **Todos los** Recopila rastrear mensajes de tipo grave, error, advertencia, detallado y la información de depuración en el registro para el proveedor definido.
    
  - **Grave** Recopila sólo los mensajes de seguimiento definidos como "Grave".
    
  - **Error** Recopila sólo los mensajes de seguimiento que se define como "Error" o "Error grave".
    
  - **Advertencia** Recopila los mensajes de seguimiento de tipo "Advertencia", "Error" y "Fatal".
    
  - **Info** Recopila sólo los mensajes de seguimiento que indican los mensajes de advertencia, error y un mensaje informativo para el proveedor definido, el más grave.
    
  - **Detallado** Recopila todos los mensajes de traza de tipo grave, de error, advertencia y detallado para el proveedor definido.
    
  - **Depurar** es básicamente un equivalente de 'All' - recopila trazas de tipo grave, Error, advertencia, información, detallado y depurar para el proveedor definido.
    
- **Indicadores** OCSLogger proporciona la opción de elegir los indicadores para cada proveedor que define qué tipo de información que puede recuperar de los archivos de seguimiento. Se pueden elegir las siguientes marcas según el proveedor:
    
  - **TF_Connection** Proporciona las entradas del registro relacionados con la conexión. Estos registros incluyen información sobre las conexiones establecidas con un componente en particular. También puede incluir información de la red relevante (esto es, relacionada con los componentes sin el concepto de una conexión).
    
  - **TF_Security** Proporciona todas las entradas de registro y eventos relacionados con la seguridad. Por ejemplo, para SipStack existen eventos de seguridad, como error de validación de dominio y errores de autenticación o autorización de clientes.
    
  - **TF_Diag** Proporciona eventos de diagnóstico que puede utilizar para diagnosticar o solucionar problemas del componente. Por el ejemplo, para SipStack, estos son errores de certificado, o errores o advertencias de DNS.
    
  - **TF_Protocol** Proporciona mensajes de protocolo, como los mensajes SIP y combinado Comunidad Codec Pack.
    
  - **TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.
    
  - **Todos los** Establece todos los indicadores disponibles disponibles para el proveedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar información acerca de los proveedores de escenario centralizado el servicio de registro existentes

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    Por ejemplo, escriba lo siguiente para revisar la información sobre el operador de las conferencias globales:
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    El comando hace que se muestre una lista de proveedores con sus marcas, configuración y componentes asociados. Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional mediante la definición de un método de salida diferentes. Para ello, escriba lo siguiente:
    
  ```
  Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
  ```

    La salida de este comando muestra a cada proveedor en un formato de cinco líneas; en cada una de ellas se indica el nombre del proveedor, el tipo de registro, el nivel de registro, las marcas, el GUID y el rol. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir un nuevo proveedor de escenario del servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logra escribiendo lo siguiente:
    
  ```
  $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
  ```

    Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
  ```

-Recopila nivel grave, error, advertencia e información de mensajes. Los indicadores utilizados son todos aquellos definidos para el proveedor de Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol.After se define la variable $LyssProvider, para utilizar con el cmdlet **New-CsClsScenario** para recopilar seguimientos del proveedor de Lyss. Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Donde $LyssProvider es la variable que contiene el escenario definido creado con **CsClsProvider de nuevo**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor de escenario del servicio de registro centralizado existente

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

El resultado final del comando es que el escenario site:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado. Puede ver el nuevo escenario con Get-CsClsScenario. Para obtener más información, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **Nuevo ClsCsProvider** no realiza una comprobación para determinar si son válidos los indicadores. Asegúrese de que la ortografía de los indicadores (por ejemplo, TF_DIAG o TF_CONNECTION) está escrita correctamente. Si los indicadores no están escritos correctamente, el proveedor no puede devolver la información del registro esperado.
  
Escriba lo siguiente si quiere agregar más proveedores a este escenario:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Donde cada proveedor definido con la directiva agregar ya se definió mediante el proceso de **CsClsProvider de nuevo** .
### <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes. Para quitar un proveedor, debe utilizar la directiva de reemplazo para el parámetro de proveedor para el **Conjunto CsClsScenario**. La única forma de quitar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update. Por ejemplo, nuestro proveedor LyssProvider tiene definido un tipo de registro WPP, un nivel establecido en Debug y las marcas TF_CONNECTION y TF_DIAG. Debe cambiar los indicadores para "Todos". Escriba lo siguiente para cambiar el proveedor:
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
  ```

  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
  ```

3. Escriba lo siguiente si quiere quitar por completo un escenario y sus proveedores asociados:
    
  ```
  Remove-CsClsScenario -Identity <scope and name of scenario>
  ```

    Por ejemplo:
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
  ```

    > [!CAUTION]
    > El cmdlet **Remove-CsClsScenario** no pedirá confirmación. El escenario se elimina junto con los proveedores que tenga asignados. Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo. No existe ningún procedimiento para recuperar escenarios o proveedores.
  
Cuando se quita un escenario mediante el cmdlet **Remove-CsClsScenario** , quitar completamente el escenario del ámbito de aplicación. Para usar los escenarios que creó y los proveedores que formaban parte de ellos, necesitará crear proveedores y asignarlos a un nuevo escenario.
## <a name="see-also"></a>Vea también

#### 

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[Nueva CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Quitar CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Conjunto de CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[Nueva CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)

