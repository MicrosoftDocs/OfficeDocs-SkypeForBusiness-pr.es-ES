---
title: 'Lync Server 2013: asignar una directiva de plan de marcado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134446"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Asignar una directiva de plan de marcado por usuario en Lync Server 2013

 


Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o del sitio para todos los usuarios habilitados para Enterprise Voice, puede omitir esta sección.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Para asignar un plan de marcado mediante el panel de control de Lync Server 2013

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios **, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar **.

5.  En la tabla, haga clic en la cuenta de usuario que desee asignar un plan de marcado.

6.  En el menú **Editar**, haga clic en **Mostrar detalles**.

7.  En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.

8.  Haga clic en **Directiva de plan de marcado** y luego seleccione el plan de marcado que desee.

9.  Haga clic en **Confirmar**.

Para obtener más información sobre cómo configurar planes de marcado, consulte el tema [Configuring dial Plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Asignar un plan de marcado por usuario mediante cmdlets de Windows PowerShell

Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet **Grant-CsdialPlan** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para asignar un plan de marcado por usuario a un solo usuario

  - El siguiente comando permite asignar el plan de marcado RedmondDialPlan al usuario Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para asignar un plan de marcado por usuario a varios usuarios

  - Este comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Para cancelar la asignación de un plan de marcado por usuario

  - Este comando desasigna cualquier plan de marcado por usuario previamente asignado a Ken Myer. Una vez desasignado el plan de marcado por usuario, Ken Myer será administrado automáticamente utilizando el plan de marcado global, su plan de marcado de sitio local (si es que existe uno) o el plan de marcado de ámbito de servicio asignado a este registrador o puerta de enlace de RTC. Los planes de marcado de ámbito de servicio tienen prioridad sobre cualquier plan de marcado de sitio local, y los planes de marcado de sitio local tienen prioridad sobre cualquier plan de marcado global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

