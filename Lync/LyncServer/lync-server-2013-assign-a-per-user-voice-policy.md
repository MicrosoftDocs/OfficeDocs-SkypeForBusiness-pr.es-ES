---
title: 'Lync Server 2013: asignar una directiva de voz por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029d9c24a5fb460128c523192c7db682e2122370
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030113"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Asignar una directiva de voz por usuario en Lync Server 2013

 


Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario de Lync Server 2013 que están habilitadas para Enterprise Voice. También puede asignar directivas de voz a usuarios específicos mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013. Use los procedimientos de este tema para asignar explícitamente directivas por usuario a los usuarios de Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Para asignar una directiva de voz específica del usuario mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en  **Usuarios ** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar ** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de voz**, seleccione la directiva de usuario que desea aplicar.
    

    > [!NOTE]  
    > La <STRONG> &lt;configuración&gt; automática</STRONG> aplica el servidor predeterminado o la configuración de directiva global.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de voz por usuario mediante cmdlets de Windows PowerShell

Puede asignar directivas de voz por usuario con Windows PowerShell y el cmdlet **Grant-CsVoicePolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Para asignar una directiva de voz por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de voz por usuario RedmondVoicePolicy al usuario Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Para asignar una directiva de voz por usuario a varios usuarios

  - Este comando asigna la directiva de voz por usuario FinanceVoicePolicy a todos los usuarios que tengan cuentas en el OU Finance de Active Directory. Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Para quitar la asignación de una directiva de voz por usuario

  - Este comando desasigna cualquier directiva de voz por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md)

