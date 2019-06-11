---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un solo usuario a la agrupación piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Puede mover un usuario del grupo de Office Communications Server 2007 R2 a su grupo de pruebas piloto de Lync Server 2013 mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013. En el ejemplo siguiente, en la columna registrar grupo, ** \<Office Communications Server\> ** es el grupo de Office Communications Server 2007 R2 y todos los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Lync Server 2013 con el panel de control de Lync Server 2013 y el shell de administración de Lync Server.

![Buscar usuarios de OCS en el panel de control de Lync Server] (images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover un usuario mediante el panel de control de Lync Server 2013

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el Panel de control de Lync Server.

3.  Haga clic en **usuarios**.

4.  En la pestaña **búsqueda de usuarios** , haga clic en el botón **Buscar** .

5.  A continuación, haga clic en **Agregar filtro**.

6.  Crear un filtro en el que el **usuario de Office Communications Server** sea igual a **true**.

7.  Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.
    
    ![Buscar usuarios de OCS en el panel de control de Lync Server] (images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Buscar usuarios de OCS en el panel de control de Lync Server")  

8.  Seleccione el usuario que desea mover al grupo de servidores de Lync Server 2013. En este ejemplo, moveremos a Sara Davis.

9.  En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.

10. En la lista desplegable, seleccione el grupo de 2013 de Lync Server.

11. Haga clic en **Acción** y, posteriormente, haga clic en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
    ![Establecer el grupo de destino en el cuadro de diálogo mover usuarios] (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Establecer el grupo de destino en el cuadro de diálogo mover usuarios")  

12. Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Lync Server 2013, lo que indica que se movió correctamente el usuario

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover un usuario mediante el shell de administración de Lync Server 2013

1.  Abra el shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

