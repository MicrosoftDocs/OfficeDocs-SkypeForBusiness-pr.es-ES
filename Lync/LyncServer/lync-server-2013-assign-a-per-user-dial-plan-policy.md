---
title: 'Lync Server 2013: asignar una directiva de plan de marcado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850746"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Asignar una directiva de plan de marcado por usuario en Lync Server 2013

 


Para completar la configuración de la cuenta de usuario para los usuarios de telefonía IP empresarial o para usuarios de conferencias de acceso telefónico local, el usuario debe tener asignado un plan de marcado. Las cuentas de usuario usarán automáticamente el plan de marcado global o, si existe alguno, el plan de marcado de nivel de sitio cuando no se asigne de forma explícita un plan de marcado por usuario existente. Si desea usar el plan de marcado global o de sitio para todos los usuarios habilitados para telefonía IP empresarial, puede omitir esta sección.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Para asignar un plan de marcado mediante el panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario a la que desea asignar un plan de marcado.

6.  En el menú **Editar**, haga clic en **Mostrar detalles**.

7.  En la página **Editar usuario de Lync Server** , en telefonía, haga clic en **telefonía** **IP empresarial**.

8.  Haga clic en **Directiva de plan de marcado**y elija el plan de marcado que quiera.

9.  Haga clic en **Confirmar**.

Para obtener más información sobre la configuración de planes de marcado, consulte el tema sobre [Cómo configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Asignar un plan de marcado por usuario mediante cmdlets de Windows PowerShell

Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet **Grant-CsdialPlan** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para asignar un plan de marcado por usuario a un único usuario

  - El comando siguiente asigna el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para asignar un plan de marcado por usuario a varios usuarios

  - Este comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Para quitar la asignación de un plan de marcado por usuario

  - El comando siguiente elimina la asignación de cualquier plan de marcado por usuario previamente asignado a Ken Myer. Después de que el plan de marcado por usuario esté sin asignar, Ken Myer se administrará automáticamente con el plan de marcado global, su plan de marcado de sitio local (si existe alguno) o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC. Un plan de marcado de ámbito de servicio tiene prioridad sobre cualquier plan de marcado del sitio, y un plan de marcado del sitio tiene prioridad sobre el plan de marcado global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

