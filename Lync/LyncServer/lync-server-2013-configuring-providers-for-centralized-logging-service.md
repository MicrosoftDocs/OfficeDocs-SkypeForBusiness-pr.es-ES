---
title: Configurar proveedores para el servicio de registro centralizado
TOCTitle: Configurar proveedores para el servicio de registro centralizado
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49889216
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar proveedores para el servicio de registro centralizado

 

_**Última modificación del tema:** 2014-03-19_

Los conceptos y la configuración de *proveedores* en el Servicio de registro centralizado son de los conocimientos más importantes que deben adquirirse. Los *proveedores* se relacionan directamente con los componentes del rol de servidor de Lync Server en el modelo de seguimiento de Lync Server. El proveedor es quien define los componentes de un servidor de Lync Server 2013 de los que se va a realizar un seguimiento, el tipo de mensajes (error irrecuperable, error o advertencia, por ejemplo) que se deben recopilar y las marcas (TF\_Connection o TF\_Diag, por ejemplo). Los proveedores son los componentes de los que se realiza un seguimiento en cada rol de servidor de Lync Server. Si usa proveedores, deberá establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.

Para ejecutar las funciones del Servicio de registro centralizado mediante el Shell de administración de Lync Server, debe ser miembro del grupo de seguridad CsAdministrator o del grupo de seguridad de control de acceso basado en roles (RBAC) CsServerAdministrator, o un rol RBAC personalizado que contenga uno de estos dos grupos. Ejecute el siguiente comando del Shell de administración de Lync Server o un símbolo del sistema de Windows PowerShell para obtener una lista de todos los roles de control de acceso basado en roles a los que este cmdlet se ha asignado (incluidos los roles de RBAC personalizados que haya creado usted mismo):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto del tema se centra en cómo definir y modificar proveedores y en qué debe contener una definición de proveedor para optimizar la solución de problemas. Existen dos maneras de emitir comandos del Servicio de registro centralizado: bien mediante CLSController.exe, que está de forma predeterminada en el directorio C:\\Archivos de programa\\Archivos comunes\\Microsoft Lync Server 2013\\CLSAgent, bien usando el Shell de administración de Lync Server para que emita comandos de Windows PowerShell. La principal diferencia entre ambos es que, cuando se usa CLSController.exe en la línea de comandos, hay una selección finita de escenarios en los que los proveedores ya están definidos y no se pueden cambiar, aunque se puede definir el nivel de registro. Si usa Windows PowerShell, en cambio, podrá definir nuevos proveedores para usarlos en las sesiones de registro y dispondrá de control total a la hora de crearlos, especificar qué datos recopilan y a qué nivel.

> [!IMPORTANT]  
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.<br />
> En lugar de hacerle indagar en profundidad en los detalles de los proveedores, el Servicio de registro centralizado proporciona una serie de escenarios ya definidos que abarcan la inmensa mayoría de los posibles problemas que pueden surgir. En casos excepciones, puede que necesite crear y definir proveedores y asignarlos a los escenarios. Es más que recomendable familiarizarse con cada uno de los escenarios antes de investigar si necesita crear nuevos proveedores y escenarios. Aquí no encontrará información detallada sobre los proveedores en sí, sino información sobre cómo crear proveedores para hacerse una idea de cómo los escenarios usan los elementos de proveedor para recabar datos de seguimiento.


Los elementos clave (descritos en [Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)) a la hora de definir un proveedor para usarlo en un escenario son los siguientes:

  - **Proveedores**   Si conoce OCSLogger, los proveedores son los componentes que se eligen para indicar a OCSLogger de qué motor de seguimiento ha de recopilar registros. Los proveedores son los mismos componentes (y, muchas veces, con los mismos nombres) que los de OCSLogger. Si no conoce OCSLogger, los proveedores son componentes específicos de un rol de servidor del que el Servicio de registro centralizado puede recopilar registros. En el caso del Servicio de registro centralizado, CLSAgent es la parte de arquitectura del Servicio de registro centralizado que efectúa el seguimiento de los componentes definidos en la configuración de proveedores.

  - **Niveles de registro**   OCSLogger ofrecía la posibilidad de escoger una serie de niveles de detalle de los datos recabados. Esta característica forma parte integral del Servicio de registro centralizado y de los escenarios, y se define mediante el parámetro **Type**. Puede elegir de entre las siguientes opciones:
    
      - **Todo**   Recopila mensajes de seguimiento de tipo error irrecuperable, error, advertencia e información en el registro correspondiente al proveedor definido.
    
      - **Irrecuperable**   Recopila solo los mensajes de seguimiento que indiquen un error relacionado con el proveedor definido.
    
      - **Error**   Recopila solo los mensajes de seguimiento que indiquen un error relacionado con el proveedor definido, además de los mensajes de error irrecuperable.
    
      - **Advertencia**   Recopila solo los mensajes de seguimiento que indiquen una advertencia relacionada con el proveedor definido, además de los mensajes de error y de error irrecuperable.
    
      - **Información**   Recopila solo los mensajes de seguimiento que sean de carácter informativo relacionados con el proveedor definido, además de los mensajes de error, error irrecuperable y advertencia.
    
      - **Detallado**   Recopila todos los mensajes de seguimiento de tipo error, error irrecuperable, advertencia e información relacionados con el proveedor definido.

  - **Marcas**   OCSLogger ofrecía la posibilidad de elegir marcas para cada proveedor que definían el tipo de información que se podía recuperar de los archivos de seguimiento. Se pueden elegir las siguientes marcas según el proveedor:
    
      - **TF\_Connection**   Proporciona entradas de registro relativas a la conexión. Estos registros incluyen información sobre las conexiones establecidas con un componente en particular. También pueden incluir información de nivel de red relevante (esto es, relacionada con componentes sin concepto de conexión).
    
      - **TF\_Security**   Proporciona todos los eventos/entradas de registro relacionados con la seguridad. Por ejemplo, para SipStack existen eventos de seguridad como error de validación de dominio y errores de autenticación/autorización de clientes.
    
      - **TF\_Diag**   Proporciona eventos de diagnóstico que pueden servir para diagnosticar o solucionar problemas con el componente. Siguiendo con el ejemplo de SipStack, existen errores de certificado y errores/advertencias de DNS.
    
      - **TF\_Protocol**   Proporciona mensajes de protocolo, como mensajes de SIP y CCCP.
    
      - **TF\_Component**   Permite crear registros de los componentes especificados como parte de los proveedores.
    
      - **All**   Define todas las marcas disponibles en relación con el proveedor.

## Para revisar la información sobre los proveedores de escenario del Servicio de registro centralizado existentes

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:
    
        Get-CsClsScenario -Identity <scope and scenario name>
    
    Por ejemplo, escriba lo siguiente para revisar la información sobre las conferencias globales:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    El comando hace que se muestre una lista de proveedores con sus marcas, configuraciones y componentes correspondientes. En caso de que no baste con la información que aparece, o la lista sea demasiado extensa para el formato de lista de Windows PowerShell predeterminado, puede mostrar más información definiendo un método de salida distinto. Para ello, escriba lo siguiente:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    El resultado de este comando muestra a cada proveedor en un formato de cinco líneas, en cada una de las cuales se indica el nombre de proveedor, tipo de registro, nivel de registro, marcas, GUID y rol.

## Para definir un nuevo proveedor de escenario del Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logra escribiendo lo siguiente:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level recopila los mensajes de error, error irrecuperable, advertencia y de carácter informativos. Las marcas utilizadas son todas las que se han definido en relación con el proveedor Lyss y engloban TF\_Connection, TF\_Diag y TF\_Protocol.

Después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimiento del proveedor Lyss. Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.

## Para cambiar un proveedor de escenario existente del Servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

El resultado final del comando es que el sitio de escenario:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado. Puede ver el nuevo escenario con Get-CsClsScenario. Para obtener información, consulte [Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario).

> [!WARNING]  
> <strong>New-ClsCsProvider</strong> no realiza comprobaciones para saber si las marcas son válidas, de modo que asegúrese de escribirlas bien (por ejemplo, TF_DIAG o TF_CONNECTION). Si están mal escritas, el proveedor no devolverá la información de registro prevista.



Escriba lo siguiente si quiere agregar más proveedores a este escenario:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Donde cada proveedor definido con la directiva Add ya se ha definido a través del proceso de **New-CsClsProvider**.

## Para quitar un proveedor de escenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes. Para eliminar un proveedor, debe usar la directiva Replace del parámetro Provider de **Set-CsClsScenario**. La única forma de eliminar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update. Por ejemplo, nuestro proveedor LyssProvider tiene definido un tipo de registro WPP, un nivel establecido en Debug y las marcas TF\_CONNECTION y TF\_DIAG. Deberá cambiar las marcas a “All”. Escriba lo siguiente para cambiar el proveedor:
    
    ```
    $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
    ```
    ```
    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
    ```

3.  Escriba lo siguiente si quiere eliminar por completo un escenario y sus proveedores correspondientes:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Por ejemplo:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    > [!WARNING]  
    > El cmdlet <strong>Remove-CsClsScenario</strong> no pide confirmación. El escenario se elimina junto con los proveedores que tenga asignados. Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo. No existe ningún procedimiento para recuperar escenarios o proveedores.
    


Cuando se elimina un escenario con el cmdlet **Remove-CsClsScenario**, se quita por completo del ámbito. Para usar los escenarios que creó y los proveedores que formaban parte de ellos, deberá crear nuevos proveedores y asignarlos a un nuevo escenario.

## Vea también

#### Otros recursos

[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider)

