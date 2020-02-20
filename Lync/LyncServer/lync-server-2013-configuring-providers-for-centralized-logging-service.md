---
title: 'Lync Server 2013: configuración de proveedores para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ba3d903b1d4a33048f5a66738897408c36a94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configuración de proveedores para el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-19_

Los conceptos y la configuración de los *proveedores* en el servicio de registro centralizado son uno de los más importantes que se deben comprender. Los *proveedores* se asignan directamente a los componentes del rol de servidor de Lync Server en el modelo de seguimiento de Lync Server. El proveedor define los componentes de un 2013 de Lync Server en los que se realizará un seguimiento, el tipo de mensajes (por ejemplo, fatal, error o Warning) que se van a recopilar y las\_marcas (por\_ejemplo, TF Connection o TF Diag). Los proveedores son los componentes que se pueden rastrear en cada rol de servidor de Lync Server. Si usa proveedores, deberá establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.

Para ejecutar las funciones del servicio de registro centralizado con el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de Estos dos grupos. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas. Hay dos formas de emitir comandos de servicio de registro centralizado. Puede usar el CLSController. exe que se encuentra, de manera predeterminada, en el directorio C:\\archivos de\\programa archivos\\comunes Microsoft Lync Server\\2013 CLSAgent. O bien, puede usar el shell de administración de Lync Server para emitir comandos de Windows PowerShell. La diferencia importante es que cuando se utiliza CLSController. exe en la línea de comandos, hay una selección finita de escenarios disponibles en los que los proveedores ya están definidos y no son modificables, pero puede definir el nivel de registro. Con Windows PowerShell, puede definir nuevos proveedores para usarlos en sus sesiones de registro y tener un control completo sobre su creación, lo que recopilan y el nivel en el que recopilan datos.

<div class="">


> [!IMPORTANT]  
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.<BR>En lugar de tener que profundizar profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted. Los escenarios proporcionados cubren la gran mayoría de los posibles problemas que se encuentren. En raras ocasiones, es posible que necesite crear y definir proveedores y asignarlos a los escenarios. Le recomendamos encarecidamente que se familiarice con cada uno de los escenarios que se proporcionan antes de investigar la necesidad de crear nuevos proveedores y escenarios. Mientras que la información sobre la creación de proveedores se encuentra aquí para familiarizarse con la forma en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, los detalles de los propios proveedores no se proporcionan en este momento.



</div>

Se incorporó en [información general del servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), los elementos clave de la definición de un proveedor para usarlo en un escenario son los siguientes:

  - **Proveedores**   si está familiarizado con OCSLogger, los proveedores son los componentes que elija para determinar OCSLogger de qué debe recopilar los registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor de los que el servicio de registro centralizado puede recopilar registros. En el caso del servicio de registro centralizado, CLSAgent es la parte de la arquitectura del servicio de registro centralizado que realiza el seguimiento de los componentes que se definen en la configuración de los proveedores.

  - **Los niveles**   de registro OCSLogger proporcionan la opción de elegir un número de niveles de detalle para los datos recopilados. Esta característica forma parte integral del servicio de registro centralizado y los escenarios, y se define mediante el parámetro **Type** . Se puede elegir entre las opciones siguientes:
    
      - **All**   recopila mensajes de seguimiento de tipo error irrecuperable, error, advertencia e información en el registro para el proveedor definido.
    
      - **Fatal**   recopila solo los mensajes de seguimiento que indican un error para el proveedor definido.
    
      - **Error**   recopila solo los mensajes de seguimiento que indican un error para el proveedor definido, además de los mensajes irrecuperables.
    
      - **ADVERTENCIA**   recopila solo los mensajes de seguimiento que indican una advertencia para el proveedor definido, además de los mensajes de error y de errores irrecuperables.
    
      - **Información**   recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, además de los mensajes de error, de errores y de advertencia.
    
      - **Verbose**   recopila todos los mensajes de seguimiento de tipo error, advertencia e información del proveedor definido.

  - **Flags**   OCSLogger proporcionó la opción de elegir marcas para cada proveedor que definió el tipo de información que podía recuperar de los archivos de seguimiento. Se pueden elegir las siguientes marcas según el proveedor:
    
      - **TF\_Connection**   proporciona entradas de registro relacionadas con la conexión. Estos registros incluyen información sobre las conexiones establecidas con un componente en particular. También pueden incluir información de nivel de red relevante (esto es, relacionada con componentes sin concepto de conexión).
    
      - **TF\_Security**   proporciona todos los eventos/entradas de registro relacionadas con la seguridad. Por ejemplo, para SipStack existen eventos de seguridad como error de validación de dominio y errores de autenticación/autorización de clientes.
    
      - **TF\_Diag**   proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente. Siguiendo con el ejemplo de SipStack, existen errores de certificado y errores/advertencias de DNS.
    
      - **TF\_Protocol**   proporciona mensajes de protocolo, como mensajes de SIP y del paquete de códecs de comunidad combinada.
    
      - **TF\_Component**   habilita el registro de los componentes especificados como parte de los proveedores.
    
      - **All**   establece todas las marcas disponibles para el proveedor.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar la información sobre los proveedores de escenario del servicio de registro centralizado existente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Por ejemplo, escriba lo siguiente para revisar la información sobre las conferencias globales:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    El comando hace que se muestre una lista de proveedores con sus marcas, configuraciones y componentes correspondientes. Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional definiendo un método de salida diferente. Para ello, escriba lo siguiente:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    El resultado de este comando muestra a cada proveedor en un formato de cinco líneas, en cada una de las cuales se indica el nombre de proveedor, tipo de registro, nivel de registro, marcas, GUID y rol.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir un nuevo proveedor de escenarios del servicio de registro centralizado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logran escribiendo lo siguiente:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level recopila los mensajes de error, error irrecuperable, advertencia y de carácter informativos. Las marcas usadas son todas las que se han definido para el proveedor Lyss e incluyen\_TF Connection,\_TF Diag and\_TF Protocol.

Después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimiento del proveedor Lyss. Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor de escenarios del servicio de registro centralizado existente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

El resultado final del comando es que el sitio de escenario:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado. Puede ver el nuevo escenario con Get-CsClsScenario. Para obtener información, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> no realiza una comprobación para determinar si las marcas son válidas. Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) está escrita correctamente. Si las marcas no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.



</div>

Escriba lo siguiente si quiere agregar más proveedores a este escenario:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Donde cada proveedor definido con la directiva Add ya se ha definido a través del proceso de **New-CsClsProvider**.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes. Para eliminar un proveedor, debe usar la directiva Replace del parámetro Provider de **Set-CsClsScenario**. La única forma de eliminar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update. Por ejemplo, nuestro proveedor LyssProvider se define con WPP como el tipo de registro, Level establecido en Debug y Flags set es\_TF Connection y\_TF diag. Deberá cambiar las marcas a “All”. Escriba lo siguiente para cambiar el proveedor:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Escriba lo siguiente si quiere eliminar por completo un escenario y sus proveedores correspondientes:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Por ejemplo:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > El cmdlet <STRONG>Remove-CsClsScenario</STRONG> no pide confirmación. El escenario se elimina junto con los proveedores que tenga asignados. Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo. No existe ningún procedimiento para recuperar escenarios o proveedores.

    
    </div>

Cuando se elimina un escenario con el cmdlet **Remove-CsClsScenario**, se quita por completo del ámbito. Para usar los escenarios que creó y los proveedores que formaban parte de ellos, deberá crear nuevos proveedores y asignarlos a un nuevo escenario.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

