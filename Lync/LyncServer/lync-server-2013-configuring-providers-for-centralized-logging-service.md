---
title: 'Lync Server 2013: configuración de proveedores para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configuración de proveedores para el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-19_

Los conceptos y la configuración de *proveedores* en el servicio de registro centralizado es uno de los más importantes para comprender. Los *proveedores* se asignan directamente a los componentes del rol servidor de Lync Server en el modelo de seguimiento de Lync Server. El proveedor define los componentes de un 2013 de Lync Server que se trazarán, el tipo de mensajes (por ejemplo, fatal, error o Warning) que se van a recopilar, así como las marcas (\_por ejemplo,\_TF Connection o TF Diag). Los proveedores son los componentes con trazabilidad de cada rol de servidor de Lync Server. Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo). El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.

Para ejecutar las funciones del servicio de registro centralizado con el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contenga cualquiera de Estos dos grupos. Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles de RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por ejemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas. Hay dos formas de emitir comandos de servicio de registro centralizados. Puede usar el CLSController. exe, que se encuentra de forma predeterminada, en el directorio C:\\archivos de\\programa archivos\\comunes Microsoft Lync Server\\2013 CLSAgent. O bien, puede usar el shell de administración de Lync Server para emitir comandos de Windows PowerShell. La distinción importante es que cuando usa CLSController. exe en la línea de comandos, hay una selección finita de escenarios disponibles en los que los proveedores ya están definidos y no son modificables, pero puede definir el nivel de registro. Al usar Windows PowerShell, puede definir nuevos proveedores para usarlos en sus sesiones de registro y tener control completo sobre su creación, qué recopilan y en qué nivel recopilan datos.

<div class="">


> [!IMPORTANT]  
> Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.<BR>En lugar de tener que profundizar profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted. Los escenarios proporcionados cubren la gran mayoría de posibles problemas que surjan. En raras ocasiones, es posible que tenga que crear y definir proveedores y asignarlos a escenarios. Le recomendamos encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear nuevos proveedores y escenarios. Aunque encontrará información sobre la creación de proveedores aquí para familiarizarse con el modo en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, en este momento no se proporcionan detalles de los propios proveedores.



</div>

Introdujo en [la información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), los elementos clave de la definición de un proveedor para usar en un escenario son los siguientes:

  - **Proveedores**   si está familiarizado con OCSLogger, los proveedores son los componentes que usted elige para indicar OCSLogger de qué debe recopilar los registros el motor de seguimiento. Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger. Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor del que el servicio de registro centralizado puede recopilar registros. En el caso del servicio de registro centralizado, CLSAgent es la parte arquitectónica del servicio de registro centralizado que realiza el seguimiento de los componentes que define en la configuración de los proveedores.

  - **Niveles de registro**   OCSLogger proporciona la opción de elegir un número de niveles de detalle para los datos recopilados. Esta característica es una parte integral del servicio de registro centralizado y los escenarios, y se define mediante el parámetro **Type** . Puede elegir entre las siguientes opciones:
    
      - **Todos**   recopila mensajes de seguimiento de tipo grave, error, warning e info en el registro para el proveedor definido.
    
      - **Error**   al recopilar solo los mensajes de seguimiento que indican un error en el proveedor definido.
    
      - **Error**   recopila solo los mensajes de seguimiento que indican un error para el proveedor definido, además de los mensajes fatales.
    
      - **ADVERTENCIA**   : recopila solo los mensajes de seguimiento que indican una advertencia para el proveedor definido, además de mensajes de error y errores graves.
    
      - **Información**   recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, más mensajes de error y de advertencia.
    
      - **Verbose**   recopila todos los mensajes de seguimiento de tipo grave, error, warning y info para el proveedor definido.

  - **Flags**   OCSLogger proporcionó la opción de elegir marcas para cada proveedor que definió el tipo de información que podría recuperar de los archivos de seguimiento. Puede elegir los siguientes marcadores, en función del proveedor:
    
      - **TF\_Connection**   proporciona entradas de registro relacionadas con la conexión. Estos registros incluyen información acerca de las conexiones establecidas a un componente determinado y desde él. También puede incluir información importante sobre el nivel de red (es decir, para los componentes sin el concepto de conexión).
    
      - **TF\_Security**   proporciona todos los eventos/entradas de registro relacionadas con la seguridad. Por ejemplo, para SipStack, estos son eventos de seguridad, como errores de validación de dominio, y errores de autenticación/autorización de clientes.
    
      - **TF\_Diag**   proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente. Por ejemplo, para SipStack, se trata de errores de certificado o advertencias o errores de DNS.
    
      - **TF\_Protocol**   proporciona mensajes de protocolo, como los mensajes de los paquetes de códecs de la comunidad por SIP y la comunidad combinada.
    
      - **TF\_Component**   habilita el registro de los componentes especificados como parte de los proveedores.
    
      - **Todos**   establece todas las marcas disponibles para el proveedor.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Para revisar la información sobre los proveedores de escenarios del servicio de registro centralizado existentes

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para revisar la configuración de proveedores existentes, escriba lo siguiente:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Por ejemplo, para revisar la información sobre el operador de conferencia global, escriba:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    El comando muestra una lista de proveedores con los indicadores, la configuración y los componentes asociados. Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional definiendo un método de salida diferente. Para ello, escriba lo siguiente:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    La salida de este comando muestra cada proveedor mostrado en un formato de cinco líneas con el nombre del proveedor, el tipo de registro, el nivel de registro, las marcas, el GUID y el rol, cada uno en una línea independiente.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Para definir un nuevo proveedor de escenarios de servicio de registro centralizado

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Un proveedor de escenarios consta de un componente para el seguimiento, las marcas que se van a usar y un nivel de detalle que se va a recopilar. Para ello, escriba:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Por ejemplo, una definición de proveedor de seguimiento que define lo que se debe recopilar y el nivel de detalle del proveedor de Lyss es similar a:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

El nivel – recopila los mensajes de error, advertencia e informativos. Los indicadores utilizados son todos los definidos para el proveedor Lyss, e incluyen TF\_Connection, TF\_Diag y TF\_Protocol.

Después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar los seguimientos del proveedor de Lyss. Para completar la creación y asignación del proveedor a un nuevo escenario, escriba:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Para cambiar un proveedor de escenarios de servicio de registro centralizado existente

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para actualizar o cambiar la configuración de un proveedor existente, escriba:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    A continuación, debe actualizar el escenario para asignar el proveedor escribiendo lo siguiente:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

El resultado final del comando es que el sitio del escenario: Redmond/RedmondLyssInfo tendrá marcas y niveles actualizados para el proveedor que se le haya asignado. Puede ver el nuevo escenario con get-CsClsScenario. Para obtener más información, vea [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> no comprueba si los marcadores son válidos. Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) esté escrita correctamente. Si los marcadores no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.



</div>

Si desea agregar proveedores adicionales a este escenario, escriba lo siguiente:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Donde cada proveedor definido con la Directiva Add ya se ha definido mediante el proceso **New-CsClsProvider** .

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Para quitar un proveedor de escenarios

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Los cmdlets proporcionados le permiten actualizar proveedores existentes y crear nuevos proveedores. Para quitar un proveedor, debe usar la Directiva Replace para que el parámetro Provider **establezca-CsClsScenario**. La única forma de quitar un proveedor por completo es reemplazarlo por un proveedor redefinido con el mismo nombre y utilizar la Directiva de actualización. Por ejemplo, nuestro proveedor LyssProvider se define con WPP como el tipo de registro, Level establecido en Debug y set Flags es\_TF Connection y\_TF diag. Debe cambiar las marcas a "todo". Para cambiar el proveedor, escriba lo siguiente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Si desea quitar por completo un escenario y los proveedores asociados a él, escriba lo siguiente:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Por ejemplo:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > El cmdlet <STRONG>Remove-CsClsScenario</STRONG> no le solicita confirmación. El escenario se elimina, junto con los proveedores que se le asignaron. Puede volver a crear el escenario volviendo a ejecutar los comandos usados para crearlo inicialmente. No hay ningún procedimiento para recuperar los escenarios o proveedores eliminados.

    
    </div>

Al quitar un escenario mediante el cmdlet **Remove-CsClsScenario** , se elimina completamente el escenario del ámbito. Para usar los escenarios que ha creado y los proveedores que forman parte del escenario, cree nuevos proveedores y asígnelos a un nuevo escenario.

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

