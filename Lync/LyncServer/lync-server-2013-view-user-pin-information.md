---
title: 'Lync Server 2013: ver información de PIN de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1e6f8e12e7b6d2dde684a4cf558eec0ece216a9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Ver información de PIN de usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Lync Server 2013 con credenciales de servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN). Puede ver la información del PIN de un usuario desde el panel de control de Lync Server 2013.

<div>


> [!NOTE]  
> Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado. Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos de establecer el <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">PIN de conferencias de acceso telefónico local de un usuario en Lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Para ver el PIN de un usuario en el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Use uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        <div>
        

        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.

        
        </div>
    
    5.  Haga clic en **Buscar**.
    
    <div>
    

    > [!NOTE]  
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG>y en <STRONG>Desbloquear PIN</STRONG>.

    
    </div>

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Ver información de PIN de usuario mediante cmdlets de Windows PowerShell

Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-user-pin-information"></a>Para ver la información del PIN del usuario

  - Para ver la información de PIN de un usuario, escriba un comando similar al siguiente en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Devolverá información similar a la siguiente:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar el PIN de conferencias de acceso telefónico local de un usuario en Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Bloquear o desbloquear un PIN de usuario en Lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

