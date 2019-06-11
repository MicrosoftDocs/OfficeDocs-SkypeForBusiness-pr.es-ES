---
title: Mover varios usuarios a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios a la agrupación piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Puede mover varios usuarios de su grupo de 2010 de Lync Server a su grupo piloto de Lync Server 2013 con el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Para mover varios usuarios con el panel de control de Lync Server 2013

1.  Abra el **Panel de control de Lync Server**.

2.  Haga clic en **Usuarios**, haga clic en Buscar y, posteriormente, haga clic en **Buscar**.

3.  Seleccione dos usuarios que desee mover al grupo de servidores de Lync Server 2013. En este ejemplo, se moverán los usuarios Chen Yang y Claus Hansen.
    
    ![Mover usuarios a un grupo de registros específico] (images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuarios a un grupo de registros específico")  

4.  En el menú **acción** , seleccione **mover usuarios seleccionados al grupo**.

5.  En la lista desplegable, seleccione el grupo de 2013 de Lync Server.

6.  Haga clic en **Acción** y, posteriormente, haga clic en **Mover usuarios seleccionados a grupo**. Haga clic en Aceptar.
    
    ![Cuadro de diálogo mover usuarios, conjunto de registradores de destino] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Cuadro de diálogo mover usuarios, conjunto de registradores de destino")  

7.  Compruebe que la columna del **Grupo registrador** de los usuarios contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que los usuarios se movieron correctamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Para mover varios usuarios con el shell de administración de Lync Server 2013

1.  Abra el shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover y reemplazar **FQDN de grupo\_** con el nombre del grupo de destino. En este ejemplo, moveremos a los usuarios Hao Chen y Katie Katie.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Ejemplo de cmdlet Get-CsUser de PowerShell] (images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Ejemplo de cmdlet Get-CsUser de PowerShell")  

3.  En la línea de comandos, escriba lo siguiente:
    
        Get-CsUser -Identity "User1"

4.  La identidad del **Grupo** de registradores debe apuntar ahora al grupo que especificó como **FQDN del grupo\_** en el paso anterior. La presencia de esta identidad confirma que el usuario se movió correctamente. Repita el paso para verificar que se ha movido **usuario2** .
    
    ![Resultado del cmdlet Get-UsUser-Identity de PowerShell] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet Get-UsUser-Identity de PowerShell")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Lync Server 2013

En este ejemplo, todos los usuarios han sido devueltos al grupo de servidores de Lync Server 2010 (pool01.contoso.net). Con el shell de administración de Lync Server 2013, se moverán todos los usuarios al mismo tiempo al grupo de servidores de Lync Server 2013 (pool02.contoso.net).

1.  Abra el **Shell de administración de Lync Server 2013**.

2.  En la línea de comandos, escriba:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet de PowerShell y resultados en el shell de administración] (images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet de PowerShell y resultados en el shell de administración")  

3.  A continuación, ejecute **Get-CsUser** para uno de los usuarios de la prueba piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  La identidad del **Grupo** de registradores de cada usuario apunta ahora al grupo que especificó\_como "FQDN del grupo" en el paso anterior. La presencia de esta identidad confirma que el usuario se movió correctamente.

5.  Además, podemos ver la lista de usuarios en el panel de control de Lync Server 2013 y comprobar que el valor del grupo de registradores apunta al grupo de Lync Server 2013.
    
    ![Lista de usuarios del panel de control de Lync Server 2013] (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios del panel de control de Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

