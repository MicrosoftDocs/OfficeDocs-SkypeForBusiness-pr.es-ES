---
title: Configurar un nodo de monitor para usar autenticación de servidor de confianza
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
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configuración de un nodo de monitor en Lync Server 2013 para usar la autenticación de servidor de confianza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Si el equipo nodo de observador está dentro de la red perimetral, el uso de la autenticación de servidor de confianza puede reducir en gran medida los impuestos de administración para mantener un único certificado en lugar de varias contraseñas de cuentas de usuario.

El primer paso para configurar la autenticación de servidor de confianza es crear un grupo de aplicaciones de confianza para hospedar el equipo del nodo de supervisor. Una vez creado el grupo de aplicaciones de confianza, debe configurar las transacciones sintéticas en ese nodo de observador para que se ejecuten como una aplicación de confianza.

<div>


> [!NOTE]
> Una aplicación de confianza es una aplicación con un estado de confianza que se asigna como parte de Lync Server 2013, pero que no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.



</div>

Para crear un grupo de aplicaciones de confianza, abra el shell de administración de Lync Server 2013 y ejecute un comando similar a este:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Para más información sobre los parámetros que se usan en el comando anterior, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:<BR>Get-Help New-CsTrustedApplicationPool-Full | número



</div>

Después de crear el grupo de aplicaciones de confianza, configure el equipo del nodo de supervisión para que ejecute transacciones sintéticas como aplicaciones de confianza. Esto se realiza mediante el cmdlet **New-CsTrustedApplication** y un comando similar a este:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Cuando se complete el comando anterior y se haya creado la aplicación de confianza, ejecute enable-CsTopology para asegurarse de que los cambios surtan efecto:

    Enable-CsTopology

Después de ejecutar enable-CsTopology, le recomendamos que reinicie el equipo.

Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configuración de un certificado predeterminado en el nodo de monitor

Cada nodo de monitor debe tener un certificado predeterminado asignado mediante el Asistente para la implementación de Lync Server.

**Para asignar un certificado predeterminado**

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Lync Server**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.

2.  En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server** y, a continuación, haga clic en **Ejecutar** en la solicitud de encabezado **, instalar o asignar certificado**.
    
    <div>
    

    > [!NOTE]
    > Si el botón <STRONG>Ejecutar</STRONG> está deshabilitado, es posible que primero tenga que hacer clic en <STRONG>Ejecutar</STRONG> en <STRONG>instalar almacén de configuración local</STRONG>.

    
    </div>

3.  Siga uno de estos pasos:
    
      - Si ya tiene un certificado que se puede usar como certificado predeterminado, haga clic en **predeterminado** en el Asistente para certificados y, a continuación, haga clic en **asignar**. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
      - Si necesita solicitar un certificado para usar el certificado predeterminado, haga clic en **solicitar** y, a continuación, siga los pasos del Asistente para solicitud de certificados para solicitar el certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Instalar y configurar un nodo de monitor

Una vez que haya reiniciado el equipo del nodo de supervisión y haya configurado un certificado, tendrá que ejecutar el archivo Watchernode. msi. (Debe ejecutar Watchernode. msi en un equipo donde estén instalados los dos archivos del agente de Operations Manager y los componentes principales de Lync Server 2013).

**Para instalar y configurar un nodo de monitor**

1.  Abra el shell de administración de Lync Server haciendo clic en **Inicio**, en **todos los programas**, en **Lync Server**y en **consola de administración de Lync Server**.

2.  En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione Entrar (especifique la ruta de acceso real a su copia de Watchernode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > También puede ejecutar Watchernode. msi desde una ventana de comandos. Para abrir una ventana Comandos, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y, a continuación, haga clic en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana de comandos, escriba el mismo comando anterior.

    
    </div>

Tenga en cuenta que el par de nombre y valor en la autenticación de comando anterior = TrustedServer distingue mayúsculas de minúsculas. Debe escribirla exactamente como se muestra. Se produce un error en el comando siguiente porque no usa la grafía de letras correcta:

C:\\herramientas\\Watchernode. msi Authentication = TrustedServer

Solo puede usar el modo TrustedServer con equipos que se encuentren en la red perimetral. Cuando un nodo Monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el equipo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

