---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5616dd5fc48b90c52c2733802023385441c371d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios al grupo piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Puede mover varios usuarios de su grupo de servidores de Lync Server 2010 a su grupo piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Para mover varios usuarios mediante el panel de control de Lync Server 2013

1.  Abra el **Panel de control de Lync Server**.

2.  Haga clic en **Usuarios**, Buscar y **Buscar**.

3.  Seleccione dos usuarios que desee mover al grupo de servidores de Lync Server 2013. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
    ![Mover usuarios a un grupo de registros específico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuarios a un grupo de registros específico")  

4.  En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.

5.  En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

6.  Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en Aceptar.
    
    ![Cuadro de diálogo mover usuarios, grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, grupo de registradores de destino")  

7.  Compruebe que la columna **grupo de registradores** de los usuarios ahora contiene el grupo de servidores de Lync Server 2013, lo que indica que los usuarios se movieron correctamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Para mover varios usuarios mediante el shell de administración de Lync Server 2013

1.  Abra el shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover y reemplazar el **FQDN del grupo\_** de servidores con el nombre del grupo de servidores de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Ejemplo de cmdlet Get-CsUser de PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Ejemplo de cmdlet Get-CsUser de PowerShell")  

3.  En la línea de comandos, escriba lo siguiente
    
        Get-CsUser -Identity "User1"

4.  La identidad del **grupo de registrador** ahora debe apuntar al grupo especificado como **FQDN del grupo\_** de servidores en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que se ha movido a **User2**.
    
    ![Resultado del cmdlet PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Lync Server 2013

En este ejemplo, todos los usuarios se han devuelto al grupo de servidores de Lync Server 2010 (pool01.contoso.net). Mediante el shell de administración de Lync Server 2013, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Lync Server 2013 (pool02.contoso.net).

1.  Abra el **Shell de administración de Lync Server 2013**.

2.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet de PowerShell y resultados en Shell de administración](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet de PowerShell y resultados en Shell de administración")  

3.  A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como "\_FQDN del grupo de servidores" en el paso anterior. La presencia de esta identidad confirma que se movió al usuario correctamente.

5.  Además, podemos ver la lista de usuarios en el panel de control de Lync Server 2013 y comprobar que el valor del grupo de registradores ahora apunta al grupo de servidores de Lync Server 2013.
    
    ![Lista de usuarios del panel de control 2013 de Lync Server](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios del panel de control 2013 de Lync Server")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

