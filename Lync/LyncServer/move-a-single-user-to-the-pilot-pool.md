---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un solo usuario a la agrupación piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Puede mover un usuario de su grupo de 2010 de Lync Server a su grupo de pruebas piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013. En el ejemplo siguiente, en la columna registrar grupo, **pool01.contoso.net** es el grupo de servidores de Lync Server 2010 y todos los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Lync Server 2013 con el panel de control de Lync Server 2013 y el shell de administración de Lync Server.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover un usuario mediante el panel de control de Lync Server 2013

**Lista de usuarios en el panel de control de Lync Server 2013**

![Panel de control de Lync Server, cuadro de diálogo mover usuario] (images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panel de control de Lync Server, cuadro de diálogo mover usuario")

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el **Panel de control de Lync Server**.

3.  Haga clic en **Usuarios**, haga clic en Buscar y, posteriormente, haga clic en **Buscar**.

4.  Seleccione el usuario que desea mover al grupo de servidores de Lync Server 2013. En este ejemplo, moveremos a Sara Davis.

5.  En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.

6.  En la lista desplegable, seleccione el grupo de 2013 de Lync Server.

7.  Haga clic en **Acción** y, posteriormente, haga clic en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
    ![Cuadro de diálogo mover usuarios, conjunto de registradores de destino] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, conjunto de registradores de destino")  

8.  Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que el usuario se ha movido correctamente.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover un usuario mediante el shell de administración de Lync Server 2013

1.  Abra el shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  A continuación, en la línea de comandos, escriba lo siguiente:
    
        Get-CsUser -Identity "David Pelton"

4.  La identidad de **RegistrarPool** apunta ahora al grupo de servidores de Lync 2013. La presencia de esta identidad confirma que el usuario se movió correctamente.
    
    ![Resultado del cmdlet Get-CsUser con el filtro de identidad] (images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro de identidad")  
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles sobre el cmdlet <STRONG>Get-CsUser</STRONG> , ejecute: <STRONG>Get-Help Get-CsUser-</STRONG> Detailed

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

