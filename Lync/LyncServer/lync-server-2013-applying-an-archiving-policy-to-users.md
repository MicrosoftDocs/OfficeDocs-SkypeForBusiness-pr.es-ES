---
title: 'Lync Server 2013: aplicar una directiva de archivado a los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Aplicar una directiva de archivado a los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Si se ha habilitado un usuario para Lync Server 2013 y ha creado una o más directivas de usuario para archivar para usuarios alojados en Lync Server 2013, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas apropiadas a esos usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla a al menos un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Lync Server 2013 del usuario.

<div>


> [!NOTE]  
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado. Para obtener más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</A> en la documentación de operaciones.



</div>

Use el procedimiento de este tema para aplicar una directiva de usuario de archivado creada previamente a una o más cuentas de usuario o grupos de usuarios.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de archivado a una cuenta de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** , en **Directiva**de archivado, seleccione la Directiva de usuario de archivado que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La <STRONG> &lt;configuración&gt; automática</STRONG> aplica la configuración predeterminada de la instalación del servidor. El servidor aplica automáticamente esta configuración.

    
    </div>

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de archivado por usuario mediante cmdlets de Windows PowerShell

Las directivas de archivado por usuario se pueden asignar mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para asignar una directiva de archivado por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para asignar una directiva de archivado por usuario a varios usuarios

  - Este comando asigna el RedmondArchivingPolicy de directiva de archivado por usuario a todos los usuarios que tienen cuentas alojadas en el registro de la agrupación de atl-cs-001.litwareinc.com. Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Para asignar una directiva de archivado por usuario

  - El comando siguiente elimina la asignación de cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar el archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

