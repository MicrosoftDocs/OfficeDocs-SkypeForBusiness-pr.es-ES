---
title: 'Lync Server 2013: Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523907fbf4bc4cca93be8e529b6b607b43f0ea87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Si se ha habilitado un usuario para Lync Server, puede configurar la Federación SIP, la Federación XMPP, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública (mi) en el panel de control de Lync Server aplicando las directivas apropiadas a usuarios específicos. Por ejemplo, si creó una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Lync Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.

<div>


> [!NOTE]  
> Para admitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuario externo que desee admitir, así como configurar las directivas apropiadas y otras opciones para controlar su uso. Para obtener más información, vea configuración de la <A href="lync-server-2013-configuring-support-for-external-user-access.md">compatibilidad con el acceso de usuarios externos en Lync server 2013</A> en la documentación de implementación o <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">administrar la Federación y el acceso externo a Lync Server 2013</A> en la documentación de operaciones.



</div>

Use el procedimiento de este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o más cuentas de usuario.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** , en **Directiva de acceso externo**, seleccione la Directiva de usuario que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La <STRONG> &lt;configuración&gt; automática</STRONG> aplica el servidor predeterminado o la configuración de la directiva global.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignar directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell

Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna el RedmondExternalAccessPolicy de directiva de acceso externo por usuario al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna el USAExternalAccessPolicy de directiva de acceso externo por usuario a todos los usuarios que tienen cuentas en la OU de Estados Unidos en Active Directory. Para obtener más información sobre el parámetro de Uo que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando elimina la asignación de una directiva de acceso externo por usuario asignada previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

