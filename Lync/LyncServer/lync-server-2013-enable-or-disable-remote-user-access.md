---
title: 'Lync Server 2013: Habilitar y deshabilitar el acceso de usuarios remotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 476cc3b90a2fdb603303789f3f9bfceb67766f5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los usuarios remotos son usuarios de su organización que tienen una identidad de Active Directory persistente dentro de la organización. Los usuarios remotos suelen iniciar sesión en Lync Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización. Los usuarios remotos incluyen empleados que trabajan en casa o que están de viaje y otros trabajadores remotos, como proveedores de confianza, a los que se les han concedido credenciales empresariales. Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Lync Server.

Para admitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos. Cuando se habilita el acceso de usuarios remotos, se habilita para toda la organización. Si posteriormente desea evitar el acceso de usuarios remotos de forma temporal o permanente, puede deshabilitarlo para su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos a su organización.

<div>


> [!NOTE]  
> Habilitar el acceso de usuarios remotos solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en la mensajería instantánea (mi) ni en conferencias de su organización hasta que también configure en menos una directiva para administrar el uso del acceso de usuarios remotos. La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. Para obtener más información sobre cómo configurar directivas para el uso de acceso de usuarios remotos, vea <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios remotos a su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios remotos a su organización, seleccione la casilla de verificación **Habilitar el acceso de usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos a su organización, desactive la casilla **Habilitar el acceso de usuarios remotos** .

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Lync Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios remotos. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) en la documentación de implementación o en la documentación de operaciones.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets de Windows PowerShell

El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-remote-user-access"></a>Para habilitar el acceso de usuarios remotos

  - Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Para deshabilitar el acceso de usuarios remotos

  - Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

