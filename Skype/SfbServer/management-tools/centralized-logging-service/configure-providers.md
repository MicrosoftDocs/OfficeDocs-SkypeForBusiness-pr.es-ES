---
title: Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumen: Aprenda a configurar proveedores de escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: e2c633dabf30ffbc42fa90066bf469e10dc25fb6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816609"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a configurar proveedores de escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.
  
Los conceptos y la configuración de proveedores en el servicio de registro centralizado es uno de los más importantes para comprender. Los proporcionantes se asignan directamente a los componentes de rol de servidor de Skype empresarial Server en el modelo de seguimiento de Skype empresarial Server. El proveedor define los componentes de un servidor de Skype empresarial 2015 en el que se realizará el seguimiento, el tipo de mensajes (por ejemplo, fatal, error o Warning) que se van a recopilar, así como las marcas (por ejemplo, TF_Connection o TF_Diag). Los proveedores son los componentes que se pueden rastrear en cada rol de servidor de Skype empresarial Server. Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.
  
Para ejecutar las funciones del servicio de registro centralizado con el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contiene alguno de estos dos grupos. Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o Windows PowerShell deba
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas. Hay dos formas de emitir comandos de servicio de registro centralizados. Puede usar el CLSController. exe, que está ubicado, de forma predeterminada, en el directorio C:\Archivos de Programa\archivos Files\Skype para empresas Server 2015 \ CLSAgent. O bien, puede usar el shell de administración de Skype empresarial Server para emitir comandos de Windows PowerShell. Al usar Windows PowerShell, puede definir nuevos proveedores para usarlos en sus sesiones de registro y tener control completo sobre su creación, qué recopilan y en qué nivel recopilan datos.
  
> [!IMPORTANT]
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos. 
  
En lugar de tener que profundizar profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted. Los escenarios proporcionados cubren la gran mayoría de posibles problemas que surjan. En raras ocasiones, es posible que tenga que crear y definir proveedores y asignarlos a escenarios. Le recomendamos encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear nuevos proveedores y escenarios. Aunque encontrará información sobre la creación de proveedores aquí para familiarizarse con el modo en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, en este momento no se proporcionan detalles de los propios proveedores. 
  
Introducido en el [servicio de registro centralizado en Skype empresarial 2015](centralized-logging-service.md), los elementos clave de la definición de un proveedor para su uso en un escenario son:
  
- **Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que usted elige para indicar OCSLogger de qué debe recopilar los registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor del que el servicio de registro centralizado puede recopilar registros. En el caso del servicio de registro centralizado, CLSAgent es la parte arquitectónica del servicio de registro centralizado que realiza el seguimiento de los componentes que define en la configuración de los proveedores.
    
- **Niveles de registro** OCSLogger proporcionó la opción de elegir un número de niveles de detalle para los datos recopilados. Esta característica es una parte integral del servicio de registro centralizado y los escenarios, y se define mediante el parámetro **Type** . Puede elegir entre las siguientes opciones:
    
  - **Todas las** Recopila mensajes de seguimiento de tipo grave, error, warning, verbose e información de depuración en el registro para el proveedor definido.
    
  - **Error grave** Recopila solo los mensajes de seguimiento definidos como "fatales".
    
  - **Error** Recopila solo los mensajes de seguimiento definidos como "error" o "fatal".
    
  - **ADVERTENCIA** Recopila solo los mensajes de seguimiento de tipo "WARNING", "error" y "fatal".
    
  - **Información** Recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, además de mensajes de error, de errores y advertencias.
    
  - **Detallado** Recopila todos los mensajes de seguimiento de tipo grave, error, warning y verbose para el proveedor definido.
    
  - **Depurar** es esencialmente un equivalente de ' All ': recopila rastros de tipo grave, error, warning, info, verbose y Debug para el proveedor definido.
    
- **Marcas** OCSLogger proporcionó la opción de elegir marcas para cada proveedor que definió el tipo de información que podría recuperar de los archivos de seguimiento. Puede elegir los siguientes marcadores, en función del proveedor:
    
  - **TF_Connection** Proporciona entradas de registro relacionadas con la conexión. Estos registros incluyen información acerca de las conexiones establecidas a un componente determinado y desde él. También puede incluir información importante sobre el nivel de red (es decir, para los componentes sin el concepto de conexión).
    
  - **TF_Security** Proporciona todos los eventos/entradas de registro relacionadas con la seguridad. Por ejemplo, para SipStack, estos son eventos de seguridad, como errores de validación de dominio, y errores de autenticación/autorización de clientes.
    
  - **TF_Diag** Proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente. Por ejemplo, para SipStack, se trata de errores de certificado o advertencias o errores de DNS.
    
  - **TF_Protocol** Proporciona mensajes de protocolo, como los mensajes de los paquetes de códec de la comunidad combinada y SIP.
    
  - **TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.
    
  - **Todas las** Establece todas las marcas disponibles para el proveedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar la información sobre los proveedores de escenarios del servicio de registro centralizado existentes

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para revisar la configuración de proveedores existentes, escriba lo siguiente:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Por ejemplo, para revisar la información sobre el operador de conferencia global, escriba:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    El comando muestra una lista de proveedores con los indicadores, la configuración y los componentes asociados. Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional definiendo un método de salida diferente. Para ello, escriba lo siguiente:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    La salida de este comando muestra cada proveedor mostrado en un formato de cinco líneas con el nombre del proveedor, el tipo de registro, el nivel de registro, las marcas, el GUID y el rol, cada uno en una línea independiente. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir un nuevo proveedor de escenarios de servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Un proveedor de escenarios consta de un componente para el seguimiento, las marcas que se van a usar y un nivel de detalle que se va a recopilar. Para ello, escriba:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Por ejemplo, una definición de proveedor de seguimiento que define lo que se debe recopilar y el nivel de detalle del proveedor de Lyss es similar a:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

El nivel obtiene mensajes de error, advertencia e información. Los indicadores que se usan son todos los definidos para el proveedor de Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol. después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimientos del proveedor de Lyss. Para completar la creación y asignación del proveedor a un nuevo escenario, escriba:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor de escenarios de servicio de registro centralizado existente

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para actualizar o cambiar la configuración de un proveedor existente, escriba:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    A continuación, debe actualizar el escenario para asignar el proveedor escribiendo lo siguiente:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

El resultado final del comando es que el sitio del escenario: Redmond/RedmondLyssInfo tendrá marcas y niveles actualizados para el proveedor que se le haya asignado. Puede ver el nuevo escenario con get-CsClsScenario. Para obtener más información, vea [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** no comprueba si los marcadores son válidos. Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) esté escrita correctamente. Si los marcadores no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.
  
Si desea agregar proveedores adicionales a este escenario, escriba lo siguiente:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Donde cada proveedor definido con la Directiva Add ya se ha definido mediante el proceso **New-CsClsProvider** .
### <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenarios

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Los cmdlets proporcionados le permiten actualizar proveedores existentes y crear nuevos proveedores. Para quitar un proveedor, debe usar la Directiva Replace para que el parámetro Provider **establezca-CsClsScenario**. La única forma de quitar un proveedor por completo es reemplazarlo por un proveedor redefinido con el mismo nombre y utilizar la Directiva de actualización. Por ejemplo, nuestro proveedor LyssProvider se define con WPP como el tipo de registro, Level establecido en debug, y los indicadores establecidos son TF_CONNECTION y TF_DIAG. Debe cambiar las marcas a "todo". Para cambiar el proveedor, escriba lo siguiente:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Si desea quitar por completo un escenario y los proveedores asociados a él, escriba lo siguiente:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Por ejemplo:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > El cmdlet **Remove-CsClsScenario** no le solicita confirmación. El escenario se elimina, junto con los proveedores que se le asignaron. Puede volver a crear el escenario volviendo a ejecutar los comandos usados para crearlo inicialmente. No hay ningún procedimiento para recuperar los escenarios o proveedores eliminados.
  
Al quitar un escenario mediante el cmdlet **Remove-CsClsScenario** , se elimina completamente el escenario del ámbito. Para usar los escenarios que ha creado y los proveedores que forman parte del escenario, cree nuevos proveedores y asígnelos a un nuevo escenario.
## <a name="see-also"></a>Vea también

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
