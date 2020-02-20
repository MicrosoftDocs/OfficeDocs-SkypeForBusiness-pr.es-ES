---
title: 'Lync Server 2013: habilitar o deshabilitar el acceso de usuarios remotos'
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
ms.openlocfilehash: 818e1189c042748409fbb86e2d3f260a11dd7211
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los usuarios remotos son usuarios de la organización que tienen una identidad persistente de Active Directory en la organización. Los usuarios remotos a menudo inician sesión en Lync Server desde fuera de la red mediante el uso de una red privada virtual (VPN) cuando no están conectados a la red de su organización. Entre los usuarios se encuentran los empleados que trabajan en casa o fuera de la oficina, así como otros trabajadores remotos, como los proveedores de confianza, a los que se conceden credenciales corporativas. Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse mediante una VPN para colaborar con los usuarios internos mediante Lync Server.

Si más adelante desea impedir de forma provisional o definitiva el acceso a usuarios de dominios federados, deshabilite la federación para la organización. Para habilitar o deshabilitar el acceso de usuarios federados en su organización, siga el procedimiento de esta sección, que también incluye las opciones de federación adecuadas que debe admitir la organización.

<div>


> [!NOTE]  
> Al habilitar el acceso de usuarios remotos solo se especifica que los servidores que ejecuten el servicio perimetral de acceso permitan la comunicación con usuarios remotos, pero dichos usuarios no pueden participar en mensajes instantáneos ni en conferencias de la organización hasta que también se configure una directiva para administrar el uso del acceso de usuarios remotos. La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto. Para más información sobre cómo configurar directivas para el uso del acceso de usuarios remotos, vea <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure Policies to control remote User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios remotos en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios remotos en la organización, active la casilla **Habilitar el acceso remoto de usuarios**.
    
      - Para deshabilitar el acceso remoto de usuarios en la organización, desactive la casilla **Habilitar el acceso remoto de usuarios**.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Lync Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos. Para obtener más información, vea [Configure Policies to control remote User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) en la documentación sobre implementación o sobre operaciones.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitación o deshabilitación del acceso de usuarios remotos mediante cmdlets de Windows PowerShell

El acceso de usuarios remotos se puede administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-remote-user-access"></a>Para habilitar el acceso de usuarios remotos

  - Para habilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Para deshabilitar el acceso de usuarios remotos

  - Para inhabilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

