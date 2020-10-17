---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd0fbebffea5553cc461f71cf67843dae0a8ae6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500227"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios al grupo piloto

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Puede mover varios usuarios desde el grupo de servidores de Office Communications Server 2007 R2 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Para mover varios usuarios mediante el panel de control de Lync Server 2013

1.  Abra el **Panel de control de Lync Server**.

2.  En la pestaña **Búsqueda de usuario**, haga clic en el botón **Buscar**.

3.  A continuación, haga clic en **Agregar filtro**.

4.  Cree un filtro donde el **usuario de servidor Office Communications Server** es igual a **Verdadero**.

5.  Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.

6.  Seleccione dos usuarios que desee mover al grupo de servidores de Lync Server 2013. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
    ![Lista de usuarios que se muestra al buscar usuarios de OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Lista de usuarios que se muestra al buscar usuarios de OCS")  

7.  En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.

8.  En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

9.  Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en Aceptar.
    
    ![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")  

10. Compruebe que la columna **grupo de registradores** de los usuarios ahora contiene el grupo de servidores de Lync Server 2013, lo que indica que los usuarios se movieron correctamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Para mover varios usuarios mediante el shell de administración de Lync Server 2013

1.  Abra el shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover y reemplazar el ** \_ FQDN del grupo** de servidores con el nombre del grupo de servidores de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de ejemplo para mover un usuario heredado](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet de ejemplo para mover un usuario heredado")  

3.  En la línea de comandos, escriba lo siguiente
    
        Get-CsUser -Identity "User1"

4.  La identidad del **grupo de registrador** ahora debe apuntar al grupo especificado como ** \_ FQDN del grupo** de servidores en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que se ha movido a **User2**.
    
    ![Resultado del cmdlet Get-UsUser de identidad de PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet Get-UsUser de identidad de PowerShell")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Lync Server 2013

En este ejemplo, todos los usuarios se han devuelto al grupo de Office Communications Server 2007 R2 (pool01.contoso.net). Mediante el shell de administración de Lync Server 2013, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Lync Server 2013 (pool02.contoso.net).

1.  Abra el **Shell de administración de Lync Server 2013**.

2.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de ejemplo para mover todos los usuarios heredados de un grupo de servidores](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet de ejemplo para mover todos los usuarios heredados de un grupo de servidores")  

3.  A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como " \_ FQDN del grupo de servidores" en el paso anterior. La presencia de esta identidad confirma que se movió al usuario correctamente.

5.  Además, podemos ver la lista de usuarios en el panel de control de Lync Server 2013 y comprobar que el valor del grupo de registradores ahora apunta al grupo de servidores de Lync Server 2013.
    
    ![Lista de usuarios del panel de control 2013 de Lync Server](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios del panel de control 2013 de Lync Server")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

