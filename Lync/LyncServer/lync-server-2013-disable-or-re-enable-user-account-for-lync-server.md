---
title: 'Lync Server 2013: deshabilitar o volver a habilitar la cuenta de usuario para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-04_

Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada previamente en Lync Server 2013 sin perder la configuración de Lync Server que ha configurado para la cuenta de usuario. Como no pierde la configuración de la cuenta de usuario de Lync Server, puede volver a habilitar otra cuenta de usuario habilitada previamente sin tener que volver a configurar la cuenta de usuario.

<div>


> [!WARNING]  
> Simplemente deshabilitar una cuenta de usuario en Active Directory <STRONG>no</STRONG> impedirá que un usuario pueda iniciar sesión o usar Lync Server. Esto se debe a que Lync usa la autenticación de certificados que optimiza el proceso de autenticación y estos certificados de cliente son válidos durante 180 días. Si desea detener la deshabilitación de las cuentas de Active Directory que se han habilitado para que Lync tenga acceso a Lync Server, debe usar el cmdlet <STRONG>Disable-CsUser</STRONG> , o el <STRONG>Panel de control de Lync Server</STRONG> , como se indica en este artículo. Una vez que el usuario está deshabilitado en Lync y el almacén central de administración se ha replicado en el entorno, los usuarios ya no podrán iniciar sesión. Además, se desconectarán los usuarios que hayan iniciado sesión.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Para deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.

6.  En el menú **acción** , siga uno de estos procedimientos:
    
      - Para deshabilitar temporalmente la cuenta de usuario de Lync Server 2013, haga clic en **deshabilitar temporalmente para Lync Server**.
    
      - Para habilitar la cuenta de usuario de Lync Server 2013, haga clic en **volver a habilitar para Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar Windows PowerShell para deshabilitar o volver a habilitar cuentas de usuario

Las cuentas de usuario se pueden deshabilitar temporalmente y, después, volverlas a habilitar más tarde mediante el cmdlet **set-CsUser** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-disable-a-user-account"></a>Para deshabilitar una cuenta de usuario

  - Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en false ($False). Por ejemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Para volver a habilitar una cuenta de usuario

  - Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en true ($True). Por ejemplo:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Agregar y habilitar una cuenta de usuario para Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

