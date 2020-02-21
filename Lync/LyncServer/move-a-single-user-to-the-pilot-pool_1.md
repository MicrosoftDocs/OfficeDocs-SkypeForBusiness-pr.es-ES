---
title: Mover un solo usuario al grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f4e85c2f34a2e4319b14f310d2a9360cb274d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un solo usuario al grupo piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Puede mover un usuario del grupo de servidores de Office Communications Server 2007 R2 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013. En el ejemplo siguiente, en la columna de grupo de registrador, ** \<Office Communications Server\> ** es el grupo de Office Communications Server 2007 R2 y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario al grupo de servidores de Lync Server 2013 mediante el panel de control de Lync Server 2013 y el shell de administración de Lync Server.

![Buscar usuarios de OCS en el panel de control de Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover un usuario mediante el panel de control de Lync Server 2013

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abrir Panel de control de Lync Server.

3.  Haga clic en **Usuarios**.

4.  Desde la pestaña **Búsqueda de usuarios** haga clic en el botón **Buscar**.

5.  A continuación, haga clic en **Agregar filtro**.

6.  Cree un filtro donde el **usuario de servidor Office Communications Server** es igual a **Verdadero**.

7.  Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.
    
    ![Buscar usuarios de OCS en el panel de control de Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")  

8.  Seleccione un usuario que quiera mover al grupo de servidores de Lync Server 2013. En ste ejemplo, moveremos al usuario Sara Davis.

9.  En el menú  **Acción **, haga clic en  **Mover usuarios seleccionados a un grupo de servidores **.

10. En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

11. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
    ![Configuración del grupo de servidores de destino en el cuadro de diálogo mover usuarios](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configuración del grupo de servidores de destino en el cuadro de diálogo mover usuarios")  

12. Compruebe que la columna **grupo de registradores** para el usuario contiene ahora el grupo de servidores de Lync Server 2013, que indica que el usuario se movió correctamente

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover un usuario mediante el shell de administración de Lync Server 2013

1.  Abra el Shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

