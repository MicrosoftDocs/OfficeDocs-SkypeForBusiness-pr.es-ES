---
title: 'Lync Server 2013: quitar una cuenta de usuario de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11a02be3dc013ff385adfe9e0437bb5b430b905c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Quitar una cuenta de usuario de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Lync Server 2013.

<div>


> [!NOTE]  
> Eliminar un usuario provocará que pierda los parámetros que haya configurado para la cuenta de usuario. Si quiere deshabilitar temporalmente una cuenta de usuario en su lugar, consulte el tema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">sobre cómo deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Para quitar una cuenta de usuario mediante el shell de administración de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee quitar.

6.  En el menú **Acción**, seleccione **Quitar de Lync Server** y, a continuación, aparecerá un cuadro de diálogo.

7.  En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Eliminación de cuentas de usuario mediante cmdlets de Windows PowerShell

Puede eliminar cuentas de usuario con el cmdlet Disable-CsUser. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-user-account"></a>Para quitar una cuenta de usuario

  - Para quitar una cuenta de usuario, utilice el cmdlet Disable-CsUser. Por ejemplo:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Una vez que se haya ejecutado este comando, no hay manera de volver a habilitar la cuenta y las configuraciones previas. En su lugar, necesitará utilizar el cmdlet Enable-CsUser para crear una cuenta nueva para Ken Myer.

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Habilitación y deshabilitación de usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

