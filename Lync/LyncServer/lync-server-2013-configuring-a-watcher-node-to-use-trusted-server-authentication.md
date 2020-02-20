---
title: Configuración de un nodo de monitor para usar la autenticación de servidor de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50f095fef5e99a02b464babd30af69a94bbd660
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configuración de un nodo de monitor en Lync Server 2013 para usar la autenticación de servidor de confianza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Si el PC del nodo de monitor se encuentra dentro de la red perimetral, con la autenticación de servidor de confianza puede reducir considerablemente los impuestos de administración para mantener un único certificado en lugar de varias contraseñas de cuentas de usuario.

El primer paso para configurar la autenticación de servidor de confianza es crear un grupo de aplicaciones de confianza para alojar el PC del nodo de monitor. Después de haber creado el grupo de aplicaciones de confianza, debe configurar las transacciones sintéticas en ese nodo de monitor para que se ejecuten como una aplicación de confianza.

<div>


> [!NOTE]
> Una aplicación de confianza es una aplicación a la que se le asigna el estado de confianza para que se ejecute como parte de Lync Server 2013, pero que no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.



</div>

Para crear un grupo de aplicaciones de confianza, abra el shell de administración de Lync Server 2013 y ejecute un comando similar a este:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Para obtener más información sobre los parámetros utilizados en el comando anterior, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

Después de crear el grupo de aplicaciones de confianza, configure el PC del nodo de monitor para que ejecute las transacciones sintéticas como una aplicación de confianza. Esto se realiza con el cmdlet **New-CsTrustedApplication** y un comando similar a este:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Cuando finaliza el comando anterior y se haya creado la aplicación de confianza, ejecute Enable-CsTopology para asegurarse de que los cambios se han realizado:

    Enable-CsTopology

Después de ejecutar Enable-CsTopology, le recomendamos que reinicie el PC.

Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configuración de un certificado predeterminado en el nodo de monitor

Cada nodo de monitor debe tener un certificado predeterminado asignado mediante el Asistente para la implementación de Lync Server.

**Para asignar un certificado predeterminado**

1.  Haga clic en **Inicio**, en **todos los programas**, en **Lync Server**y, a continuación, en **Asistente para la implementación de Lync Server**.

2.  En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server** y, a continuación, haga clic en **Ejecutar** en el título **solicitud, instalar o asignar certificado**.
    
    <div>
    

    > [!NOTE]
    > Si el botón <STRONG>Ejecutar</STRONG> está deshabilitado, puede que primero necesite hacer clic en <STRONG>Ejecutar</STRONG> en <STRONG>Instalar el almacén de configuración local</STRONG>.

    
    </div>

3.  Siga uno de estos procedimientos:
    
      - Si ya tiene un certificado que puede usarse como certificado predeterminado, haga clic en **Predeterminado** en el Asistente para certificados y luego haga clic en **Asignar**. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
      - Si necesita solicitar un certificado para usarlo como certificado predeterminado, haga clic en **Solicitar** y luego siga los pasos del Asistente para solicitar certificados para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Instalación y configuración de un nodo de monitor

Después de haber reiniciado el PC del nodo de monitor y haber configurado un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode. msi en un equipo en el que estén instalados tanto los archivos del agente de Operations Manager como los componentes principales de Lync Server 2013).

**Para instalar y configurar un nodo de monitor**

1.  Abra el shell de administración de Lync Server; para ello, haga clic en **Inicio**, en **todos los programas**, en **Lync Server**y, a continuación, en **Shell de administración de Lync Server**.

2.  En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione Entrar (especifique la ruta de acceso real a su copia de Watchernode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > También puede ejecutar Watchernode.msi desde una ventana de comandos. Para abrir una ventana de comandos, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y luego en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana de comandos, escriba el mismo comando anterior.

    
    </div>

Nota que el par nombre-valor del anterior comando Authentication=TrustedServer distingue mayúsculas y minúsculas. Debe escribirlo exactamente como aparece. El siguiente comando tiene errores porque no usa las letras mayúsculas y minúsculas correctas:

C:\\herramientas\\Watchernode. msi Authentication = TrustedServer

El modo TrustedServer solo se puede usar con los PC que se encuentran dentro de la red perimetral. Cuando un nodo de monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el PC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

