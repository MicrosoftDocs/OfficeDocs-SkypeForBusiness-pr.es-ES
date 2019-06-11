---
title: 'Lync Server 2013: quitar una cuenta de usuario de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Quitar una cuenta de usuario de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada previamente en Lync Server 2013.

<div>


> [!NOTE]  
> Si quita un usuario, perderá la configuración que haya configurado para la cuenta de usuario. Si desea deshabilitar temporalmente una cuenta de usuario, vea el tema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">sobre cómo deshabilitar o volver a habilitar una cuenta de usuario para Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Para quitar una cuenta de usuario mediante el shell de administración de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desea quitar.

6.  En el menú **acción** , seleccione **quitar de Lync Server**y aparecerá un cuadro de diálogo.

7.  En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Quitar cuentas de usuario mediante cmdlets de Windows PowerShell

Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-user-account"></a>Para quitar una cuenta de usuario

  - Para quitar una cuenta de usuario, use el cmdlet Disable-CsUser. Por ejemplo:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Después de ejecutar este comando, no hay ninguna forma de volver a habilitar la cuenta y su configuración anterior. En su lugar, tendrá que usar el cmdlet enable-CsUser para crear una cuenta nueva para Ken Myer.

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

