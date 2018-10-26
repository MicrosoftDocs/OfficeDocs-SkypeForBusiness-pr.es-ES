---
title: Mover un solo usuario al grupo piloto
TOCTitle: Mover un solo usuario al grupo piloto
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48277044
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover un solo usuario al grupo piloto

 

_**Última modificación del tema:** 2012-09-26_

Puede mover un usuario del grupo de servidores de Lync Server 2010 al grupo piloto de Lync Server 2013 usando el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server 2013. En el ejemplo siguiente, en la columna de grupo de servidores de registro, **pool01.contoso.net** es el grupo de servidores de Lync Server 2010 y los seis usuarios están conectados a este grupo. Ejecute los procedimientos siguientes para mover un usuario al grupo de servidores de Lync Server 2013 con el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server.

## Para mover un usuario con el Panel de control de Lync Server 2013

**Lista de usuarios en el panel de control de Lync Server 2013**

![Panel de control de Lync Server, cuadro de diálogo Mover usuario](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panel de control de Lync Server, cuadro de diálogo Mover usuario")

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el **Panel de control de Lync Server**.

3.  Haga clic en **Usuarios**, haga clic en Buscar y, posteriormente, haga clic en **Buscar**.

4.  Seleccione un usuario que quiera mover al grupo Lync Server 2013. En este ejemplo, moveremos a Sara Davis.

5.  En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.

6.  En la lista desplegable, seleccione el grupo Lync Server 2013.

7.  Haga clic en **Acción** y, posteriormente, haga clic en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
    ![Mover usuarios, cuadro de diálogo de grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Mover usuarios, cuadro de diálogo de grupo de registradores de destino")  

8.  Verifique que la columna **Grupo de registradores** para el usuario ya contiene el grupo Lync Server 2013, lo cual indica que se ha movido correctamente el usuario.

## Para mover un usuario con el Shell de administración de Lync Server 2013

1.  Abra Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  A continuación, en la línea de comandos, escriba:
    
        Get-CsUser -Identity "David Pelton"

4.  Ahora, la identidad **RegistrarPool** apunta al grupo de servidores de Lync Server 2013. La presencia de esta identidad confirma que el usuario se ha movido correctamente.
    
    ![Resultado del cmdlet Get-CsUser con el filtro Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro Identity")  
    

    > [!NOTE]
    > Para más información sobre el cmdlet <STRONG>Get-CsUser</STRONG> , ejecute <STRONG>Get-Help Get-CsUser –Detailed</STRONG>


