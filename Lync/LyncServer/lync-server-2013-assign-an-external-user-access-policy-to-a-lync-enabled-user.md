---
title: 'Lync Server 2013: asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync'
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
ms.openlocfilehash: 7d7b1f9436695c5bd455c376d9c75add996be28f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508947"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Si un usuario se ha habilitado para Lync Server, puede configurar la Federación SIP, la Federación XMPP, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública en el panel de control de Lync Server, mediante la aplicación de las directivas apropiadas a usuarios específicos. Por ejemplo, si ha creado una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Lync Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.

<div>


> [!NOTE]  
> Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuarios externos que desee permitir y configurar las directivas adecuadas y otras opciones para controlar su uso. Para obtener más información, consulte Configuración de la <A href="lync-server-2013-configuring-support-for-external-user-access.md">compatibilidad para el acceso de usuarios externos en Lync server 2013</A> en la documentación de implementación o administración de la <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Federación y el acceso externo a Lync Server 2013</A> en la documentación de operaciones.



</div>

Use el procedimiento descrito en este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o varias cuentas de usuario.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en  **Usuarios ** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de acceso externo**, seleccione la directiva de usuario que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La configuración <STRONG> &lt; automática &gt; </STRONG> aplica el servidor predeterminado o la configuración de directiva global.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Asignación de directivas de acceso externo de Per-User mediante cmdlets de Windows PowerShell

Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa (OU) de los Estados Unidos en Active Directory. Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando anula la asignación de una directiva de acceso externo por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

