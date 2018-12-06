---
title: Mover un único usuario a un grupo piloto
TOCTitle: Mover un único usuario a un grupo piloto
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49889351
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover un único usuario a un grupo piloto

 

_**Última modificación del tema:** 2012-09-28_

Puede mover un usuario de su grupo Office Communications Server 2007 R2 a su grupo piloto Lync Server 2013 usando Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013. En el ejemplo anterior, en la columna de grupo de registros, el **\<servidor Office Communications Server\>** es el grupo Office Communications Server 2007 R2 y los seis usuarios se conectan a este grupo. Use los siguientes procedimientos para mover un usuario a su grupo Lync Server 2013 usando Panel de control de Lync Server 2013 y Shell de administración de Lync Server.

![Buscar usuarios de OCS en el Panel de control de Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Buscar usuarios de OCS en el Panel de control de Lync Server")

## Para mover un usuario con el Panel de control de Lync Server 2013

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra Panel de control de Lync Server.

3.  Haga clic en **Usuarios**.

4.  En la pestaña **Búsqueda de usuario**, haga clic en el botón **Buscar**.

5.  A continuación, haga clic en **Agregar filtro**.

6.  Cree un filtro en el que **Usuario de Office Communications Server** sea igual a **Verdadero**.

7.  Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.
    
    ![Buscar usuarios de OCS en el Panel de control de Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Buscar usuarios de OCS en el Panel de control de Lync Server")  

8.  Seleccione un usuario que desea mover al grupo de servidores Lync Server 2013. En este ejemplo, se moverá al usuario Sara Davis.

9.  En el menú **Acción**, seleccione **Mover usuarios seleccionados a un grupo de servidores**.

10. En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

11. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados al grupo de servidores**. Haga clic en **Aceptar**.
    
    ![Configuración del grupo de servidores de destino en el cuadro de diálogo Mover usuarios](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configuración del grupo de servidores de destino en el cuadro de diálogo Mover usuarios")  

12. Verifique que la columna **Grupo de registradores** para el nuevo usuario ahora incluya el grupo Lync Server 2013, que indica que el usuario se movió correctamente

## Para mover un usuario con el Shell de administración de Lync Server 2013

1.  Abra Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  A continuación, en la línea de comandos, escriba:
    
        Get-CsUser -Identity "David Pelton"

4.  Ahora, la identidad **RegistrarPool** apunta al grupo de servidores de Lync Server 2013. La presencia de esta identidad confirma que el usuario se ha movido correctamente.
    
    ![Resultado del cmdlet Get-CsUser con el filtro Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Resultado del cmdlet Get-CsUser con el filtro Identity")  
    

    > [!NOTE]
    > Para más información sobre el cmdlet <STRONG>Get-CsUser</STRONG>, ejecute <STRONG>Get-Help Get-CsUser –Detailed</STRONG>


