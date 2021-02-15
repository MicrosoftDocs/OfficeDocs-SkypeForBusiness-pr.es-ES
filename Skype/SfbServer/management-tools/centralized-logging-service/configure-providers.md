---
title: Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo configurar proveedores de escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835170"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar proveedores de escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015.
  
Los conceptos y la configuración de los proveedores en el servicio de registro centralizado es uno de los más importantes que se debe comprender. Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model. El proveedor define los componentes de un Skype Empresarial Server 2015 que se realizará un seguimiento, el tipo de mensajes (por ejemplo, error irresal, error o advertencia) que se van a recopilar y las marcas (por ejemplo, TF_Connection o TF_Diag). Los proveedores son los componentes que se pueden rastrear en cada rol de servidor de Skype Empresarial Server. Si usa proveedores, deberá establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.
  
Para ejecutar las funciones del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o un rol RBAC personalizado que contenga cualquiera de estos dos grupos. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado usted mismo), ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o desde el símbolo del sistema Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por ejemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas. Hay dos formas de emitir comandos del Servicio de registro centralizado. Puede usar el CLSController.exe que se encuentra, de forma predeterminada, en el directorio C:\Archivos de programa\Archivos comunes\Skype Empresarial Server 2015\CLSAgent. O bien, puede usar el Shell de administración de Skype Empresarial Server para emitir Windows PowerShell comandos. Al usar Windows PowerShell, puede definir nuevos proveedores para usarlos en las sesiones de registro y tener control total sobre su creación, lo que recopilan y en qué nivel recopilan datos.
  
> [!IMPORTANT]
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos. 
  
En lugar de requerir profundizar en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted. Los escenarios proporcionados cubren la mayoría de los posibles problemas que se encontrarán. En raras ocasiones, es posible que deba crear y definir proveedores y asignarlos a escenarios. Se recomienda encarecidamente familiarizarse con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear nuevos proveedores y escenarios. Aunque la información sobre la creación de proveedores se encuentra aquí para familiarizarse con el modo en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, no se proporcionan detalles sobre los propios proveedores en este momento. 
  
Introducido en el servicio de registro centralizado en [Skype Empresarial 2015,](centralized-logging-service.md)los elementos clave para definir un proveedor para usarlo en un escenario son:
  
- **Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que elige para decir a OCSLogger de qué debe recopilar registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor de los que el servicio de registro centralizado puede recopilar registros. En el caso del servicio de registro centralizado, CLSAgent es la parte de arquitectura del servicio de registro centralizado que está realizando el seguimiento de los componentes definidos en la configuración de proveedores.
    
- **Niveles de registro** OCSLogger proporcionaba la opción de elegir una serie de niveles de detalle para los datos recopilados. Esta característica es una parte integral del servicio de registro centralizado y los escenarios, y se define mediante el **parámetro Type.** Se puede elegir entre las opciones siguientes:
    
  - **Todos** Recopila mensajes de seguimiento de información de tipo fatal, error, advertencia, detallado y depuración en el registro del proveedor definido.
    
  - **Fatal** Recopila solo los mensajes de seguimiento definidos como "Fatal".
    
  - **Error** Recopila solo los mensajes de seguimiento definidos como "Error" o "Fatal".
    
  - **Advertencia** Recopila solo los mensajes de seguimiento de tipo "Advertencia", "Error" y "Fatal".
    
  - **Información** Recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, además de los mensajes irreales, de error y de advertencia.
    
  - **Detallado** Recopila todos los mensajes de seguimiento de tipo fatal, error, advertencia y detallado para el proveedor definido.
    
  - **Depurar** esto es básicamente un equivalente de "Todos": recopila seguimientos de tipo Fatal, Error, Warning, Info, Verbose y Debug para el proveedor definido.
    
- **Marcas** OCSLogger proporcionaba la opción de elegir marcas para cada proveedor que definiese el tipo de información que podrías recuperar de los archivos de seguimiento. Se pueden elegir las siguientes marcas según el proveedor:
    
  - **TF_Connection** Proporciona entradas de registro relacionadas con la conexión. Estos registros incluyen información sobre las conexiones establecidas con un componente en particular. También pueden incluir información de nivel de red relevante (esto es, relacionada con componentes sin concepto de conexión).
    
  - **TF_Security** Proporciona todos los eventos o entradas de registro relacionados con la seguridad. Por ejemplo, para SipStack existen eventos de seguridad como error de validación de dominio y errores de autenticación/autorización de clientes.
    
  - **TF_Diag** Proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente. Siguiendo con el ejemplo de SipStack, existen errores de certificado y errores/advertencias de DNS.
    
  - **TF_Protocol** Proporciona mensajes de protocolo, como MENSAJES SIP y Paquete de códecs de la comunidad combinada.
    
  - **TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.
    
  - **Todos** Establece todas las marcas disponibles disponibles para el proveedor.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar la información acerca de los proveedores de escenarios del Servicio de registro centralizado existente

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Por ejemplo, escriba lo siguiente para revisar la información sobre las conferencias globales:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    El comando hace que se muestre una lista de proveedores con sus marcas, configuraciones y componentes correspondientes. Si la información mostrada no es suficiente o la lista es demasiado larga para el formato de lista Windows PowerShell predeterminado, puede mostrar información adicional definiendo un método de salida diferente. Para ello, escriba lo siguiente:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    El resultado de este comando muestra a cada proveedor en un formato de cinco líneas, en cada una de las cuales se indica el nombre de proveedor, tipo de registro, nivel de registro, marcas, GUID y rol. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir un nuevo proveedor de escenarios de servicio de registro centralizado

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logran escribiendo lo siguiente:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

El -Level recopila mensajes irreales, de error, de advertencia e información. Las marcas usadas son todas las definidas para el proveedor de Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol.Una vez definida la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimientos del proveedor de Lyss. Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor de escenarios de servicio de registro centralizado existente

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

El resultado final del comando es que el sitio de escenario:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado. Puede ver el nuevo escenario con Get-CsClsScenario. Para obtener información, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** no comprueba si las marcas son válidas. Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) esté correctamente escrito. Si las marcas no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.
  
Escriba lo siguiente si quiere agregar más proveedores a este escenario:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Donde cada proveedor definido con la directiva Add ya se ha definido a través del proceso de **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenario

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes. Para eliminar un proveedor, debe usar la directiva Replace del parámetro Provider de **Set-CsClsScenario**. La única forma de eliminar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update. Por ejemplo, nuestro proveedor LyssProvider tiene definido un tipo de registro WPP, un nivel establecido en Debug y las marcas TF_CONNECTION y TF_DIAG. Debe cambiar las marcas a "Todos". Escriba lo siguiente para cambiar el proveedor:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Escriba lo siguiente si quiere eliminar por completo un escenario y sus proveedores correspondientes:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Por ejemplo:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > El cmdlet **Remove-CsClsScenario** no pide confirmación. El escenario se elimina junto con los proveedores que tenga asignados. Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo. No existe ningún procedimiento para recuperar escenarios o proveedores.
  
Cuando se elimina un escenario con el cmdlet **Remove-CsClsScenario**, se quita por completo del ámbito. Para usar los escenarios que creó y los proveedores que formaban parte de ellos, deberá crear nuevos proveedores y asignarlos a un nuevo escenario.
## <a name="see-also"></a>Vea también

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
