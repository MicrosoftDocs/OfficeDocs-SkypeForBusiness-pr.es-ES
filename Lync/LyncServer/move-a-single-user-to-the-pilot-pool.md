---
title: Mover un solo usuario al grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un solo usuario al grupo piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Puede mover un usuario de su grupo de servidores de Lync Server 2010 al grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013. En el ejemplo siguiente, en la columna de grupo de registrador, **pool01.contoso.net** es el grupo de servidores de Lync Server 2010 y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario al grupo de servidores de Lync Server 2013 mediante el panel de control de Lync Server 2013 y el shell de administración de Lync Server.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover un usuario mediante el panel de control de Lync Server 2013

**Lista de usuarios en el panel de control de Lync Server 2013**

![Panel de control de Lync Server, cuadro de diálogo mover usuario](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panel de control de Lync Server, cuadro de diálogo mover usuario")

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abrir **Panel de control de Lync Server**.

3.  Haga clic en **Usuarios**, Buscar y **Buscar**.

4.  Seleccione un usuario que quiera mover al grupo de servidores de Lync Server 2013. En ste ejemplo, moveremos al usuario Sara Davis.

5.  En el menú  **Acción **, haga clic en  **Mover usuarios seleccionados a un grupo de servidores **.

6.  En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

7.  Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
    ![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")  

8.  Compruebe que la columna **grupo de registradores** del usuario contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que el usuario se movió correctamente.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover un usuario mediante el shell de administración de Lync Server 2013

1.  Abra el Shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  A continuación, en la línea de comandos, escriba lo siguiente:
    
        Get-CsUser -Identity "David Pelton"

4.  La identidad **RegistrarPool** ahora apunta al grupo de servidores de Lync 2013. La presencia de esta identidad confirma que se movió al usuario correctamente.
    
    ![Resultado del cmdlet Get-CsUser con el filtro de identidad](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro de identidad")  
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles acerca del cmdlet <STRONG>Get-CsUser</STRONG>, ejecute: <STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

