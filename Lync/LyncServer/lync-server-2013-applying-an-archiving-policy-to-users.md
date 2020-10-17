---
title: 'Lync Server 2013: aplicar una directiva de archivado a los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423eb8c4d96496f75f8702c5cf2ccf21a3b13b8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508927"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Aplicar una directiva de archivado a los usuarios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Si un usuario se ha habilitado para Lync Server 2013 y ha creado una o varias directivas de usuario para archivar para los usuarios hospedados en Lync Server 2013, puede implementar la compatibilidad de archivado para usuarios específicos mediante la aplicación de las directivas apropiadas a los usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla al menos a un usuario o a un grupo de usuarios para que admita el archivado de las comunicaciones de Lync Server 2013 del usuario.

<div>


> [!NOTE]  
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos</A> de servidores en la documentación de operaciones.



</div>

Use el procedimiento descrito en este tema para usar una directiva de usuario de archivado creada previamente en una o varias cuentas de usuario o grupos de usuarios.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Para aplicar una directiva de archivado a un usuario o grupo de usuarios

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La configuración <STRONG> &lt; automática &gt; </STRONG> aplica la configuración de la instalación del servidor predeterminada. Esta configuración se aplica automáticamente por el servidor.

    
    </div>

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Asignación de una directiva de archivado de Per-User mediante cmdlets de Windows PowerShell

Las directivas de archivado por usuario se pueden asignar mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para asignar una directiva de archivado por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para asignar una directiva de archivado por usuario a varios usuarios

  - Con este comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas hospedadas en el grupo de registradores atl-cs-001.litwareinc.com. Para obtener más información sobre el parámetro filter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Para asignar una directiva de archivado por usuario

  - Este comando desasigna cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Administración del archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

