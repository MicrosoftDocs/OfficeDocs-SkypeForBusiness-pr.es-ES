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
description: 'Resumen: Obtenga información sobre cómo configurar los proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: bea50b6c1ea2fa805e407db4f6dd3fcfb761b4ef
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504351"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar los proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.
  
Los conceptos y la configuración de proveedores de servicio de registro centralizado es uno de los más importantes de entender. Theproviders se asignan directamente a Skype para componentes de rol de servidor de Business Server en la Skype para el modelo de seguimiento de Business Server. El proveedor define los componentes de un Skype para Business Server 2015 que se trazará, el tipo de mensajes (por ejemplo, grave, error o advertencia) para recopilar y los indicadores (por ejemplo, TF_Connection o TF_Diag). Los proveedores son los componentes puede trazar en cada Skype para el rol de servidor de Business Server. Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.
  
Para ejecutar las funciones de servicio de registro centralizado con la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos. Para devolver una lista de todas las funciones de control (RBAC) de acceso basado en roles este cmdlet se ha asignado a (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para Shell de administración de servidor empresarial o Windows PowerShell símbolo del sistema:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

En el resto de este tema se centra en cómo definir proveedores, modificar un proveedor y lo que contiene una definición de proveedor para optimizar su resolución de problemas. Hay dos formas para emitir los comandos de servicio de registro centralizado. Puede usar el CLSController.exe que se encuentra, de forma predeterminada, en el directorio C:\Program Files\Common Files\Skype para 2015\CLSAgent Business Server. O bien, puede usar el Skype para Shell de administración de servidor empresarial para emitir los comandos de Windows PowerShell. Mediante el uso de Windows PowerShell, puede definir nuevos proveedores para su uso en las sesiones de registro y tiene control completo sobre su creación, lo que recopilan, y en qué nivel recopilan datos.
  
> [!IMPORTANT]
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos. 
  
En lugar de que tenga que realizar profundamente profundiza en los detalles de los proveedores, el servicio de registro centralizado proporciona un número de escenarios que ya se han definido por usted. Los escenarios proporcionados cubren la mayoría de los posibles problemas que se va a encontrar. En algunos casos poco frecuentes, debe crear y definir los proveedores y asignarlas a escenarios. Se recomienda encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear escenarios y proveedores de nuevo. Mientras se encuentre la información sobre la creación de proveedores aquí para familiarizarse con los escenarios de usan que los elementos de proveedor para recopilar información de seguimiento, no se proporcionan detalles sobre los proveedores de sí mismos en este momento. 
  
Introducidos en el [Servicio de registro centralizado en Skype para profesionales de 2015](centralized-logging-service.md), los elementos clave de la definición de un proveedor para su uso en un escenario son:
  
- **Proveedores de** Si está familiarizado con OCSLogger, los proveedores son los componentes que elija para indicar a OCSLogger el motor de seguimiento de qué debe recopilar los registros de. Los proveedores son los mismos componentes (y, muchas veces, con los mismos nombres) que los de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son roles de servidor de componentes específicos que el servicio de registro centralizado puede recopilar los registros de. En el caso del servicio centralizado de registro, el con CLSAgent es la parte de arquitectura del servicio de registro centralizado que está realizando el seguimiento de los componentes que se definen en la configuración de proveedores.
    
- **Niveles de registro** OCSLogger proporciona la opción para elegir un número de niveles de detalle de los datos recopilados. Esta característica es una parte integral del servicio de registro centralizado y escenarios y se define mediante el parámetro de **tipo** . Puede elegir entre las siguientes opciones:
    
  - **Todos los** Recopila seguimiento de mensajes de tipo grave, error, advertencia, detallado e información de depuración en el registro para el proveedor definido.
    
  - **Graves** Recopila sólo los mensajes de seguimiento definidos como "Grave".
    
  - **Error** Recopila sólo los mensajes de seguimiento se definen como "Error" o "Error grave".
    
  - **Advertencia** Recopila sólo los mensajes de seguimiento de tipo "Warning", "Error" y "Grave".
    
  - **Info** Recopila sólo los mensajes de seguimiento que indiquen un mensaje informativo para el proveedor definido, además de grave, error y los mensajes de advertencia.
    
  - **Detallado** Recopila todos los mensajes de seguimiento de error grave, tipo, advertencia y detallado para el proveedor definido.
    
  - **Depurar** es básicamente un equivalente de 'All' - recopila seguimientos de tipo Error grave, Error, advertencia, información, detallado y depurar el proveedor definido.
    
- **Marcas** OCSLogger proporciona la opción para elegir los indicadores para cada proveedor que definen qué tipo de información se puede recuperar desde los archivos de seguimiento. Se pueden elegir las siguientes marcas según el proveedor:
    
  - **TF_Connection** Proporciona las entradas del registro relacionadas con la conexión. Estos registros incluyen información sobre las conexiones establecidas con un componente en particular. También puede incluir información de la red relevante (esto es, relacionada con los componentes sin el concepto de una conexión).
    
  - **TF_Security** Proporciona todas las entradas de registro y eventos relacionados con la seguridad. Por ejemplo, para SipStack existen eventos de seguridad, como error de validación de dominio y errores de autenticación o autorización de clientes.
    
  - **TF_Diag** Proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente. Por el ejemplo, para SipStack, estos son errores de certificado, o errores o advertencias de DNS.
    
  - **TF_Protocol** Proporciona los mensajes de protocolo, como los mensajes SIP y combinar Pack de códec de la Comunidad.
    
  - **TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.
    
  - **Todos los** Establece todos los indicadores disponibles disponibles para el proveedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar la información acerca de los proveedores de escenario de servicio de registro centralizado existentes

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    Por ejemplo, escriba lo siguiente para revisar la información sobre el operador de las conferencias globales:
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    El comando hace que se muestre una lista de proveedores con sus marcas, configuración y componentes asociados. Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista de Windows PowerShell de forma predeterminada, puede mostrar información adicional mediante la definición de un método de resultados diferente. Para ello, escriba lo siguiente:
    
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

-Nivel recopila grave, error, advertencia e información de los mensajes. Los indicadores utilizados son todos los definidos para el proveedor Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol.After se define la variable $LyssProvider, puede usar con el cmdlet **New-CsClsScenario** para reunir seguimientos desde el proveedor Lyss. Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor existente de escenario de servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

El resultado final del comando es que el escenario site:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado. Puede ver el nuevo escenario con Get-CsClsScenario. Para obtener información detallada, vea [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** no se comprueba para determinar si los indicadores son válidos. Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) está escrita correctamente. Si las marcas no están escritas correctamente, el proveedor no puede devolver la información de registro esperado.
  
Escriba lo siguiente si quiere agregar más proveedores a este escenario:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Donde cada proveedor definido con la directiva Add ya definida mediante el proceso de **New-CsClsProvider** .
### <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenario

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes. Para quitar un proveedor, debe utilizar la directiva de reemplazo para el parámetro de proveedor a **Set-CsClsScenario**. La única forma de quitar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update. Por ejemplo, nuestro proveedor LyssProvider tiene definido un tipo de registro WPP, un nivel establecido en Debug y las marcas TF_CONNECTION y TF_DIAG. Debe cambiar las marcas como "Todos". Escriba lo siguiente para cambiar el proveedor:
    
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
    > El cmdlet **Remove-CsClsScenario** no solicitar confirmación. El escenario se elimina junto con los proveedores que tenga asignados. Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo. No existe ningún procedimiento para recuperar escenarios o proveedores.
  
Al quitar un escenario mediante el cmdlet **Remove-CsClsScenario** , quitar completamente el escenario del ámbito de aplicación. Para usar los escenarios que creó y los proveedores que formaban parte de ellos, necesitará crear proveedores y asignarlos a un nuevo escenario.
## <a name="see-also"></a>Vea también

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)