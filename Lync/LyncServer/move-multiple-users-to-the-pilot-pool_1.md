---
title: Mover varios usuarios al grupo de servidores piloto
TOCTitle: Mover varios usuarios al grupo de servidores piloto
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49889389
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover varios usuarios al grupo de servidores piloto

 

_**Última modificación del tema:** 2012-10-02_

Puede mover varios usuarios de su grupo de Office Communications Server 2007 R2 al grupo piloto de Lync Server 2013 mediante Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para mover varios usuarios mediante el Panel de control de Lync Server 2013

1.  Abrir **Panel de control de Lync Server** .

2.  En la pestaña **Búsqueda de usuario**, haga clic en el botón **Buscar**.

3.  A continuación, haga clic en **Agregar filtro**.

4.  Cree un filtro en el que **Usuario de Office Communications Server** sea igual a **Verdadero**.

5.  Haga clic en **Buscar** para buscar usuarios heredados de Office Communications Server 2007 R2.

6.  Seleccione los dos usuarios que quiera mover al grupo de Lync Server 2013. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
    ![Lista de usuario resultante de buscar usuarios OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Lista de usuario resultante de buscar usuarios OCS")  

7.  En el menú **Acción** , seleccione **Mover usuarios seleccionados a grupo** .

8.  En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

9.  Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo** . Haga clic en Aceptar.
    
    ![Mover usuarios, cuadro de diálogo de grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Mover usuarios, cuadro de diálogo de grupo de registradores de destino")  

10. Compruebe que la columna **Grupo de registradores** de los usuarios ahora contiene el grupo Lync Server 2013, lo que indica que se ha movido correctamente a los usuarios.

## Para mover varios usuarios mediante el Shell de administración de Lync Server 2013

1.  Abra Shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba lo siguiente y sustituya **User1** y **User2** por los nombres de usuario concretos que quiere mover, y sustituya **pool\_FQDN** por el nombre del grupo de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de ejemplo para mover usuarios heredados](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet de ejemplo para mover usuarios heredados")  

3.  En la línea de comandos, escriba lo siguiente
    
        Get-CsUser -Identity "User1"

4.  Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool\_FQDN** en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que se ha movido a **User2**.
    
    ![Resultado del cmdlet de PowerShell Get-UsUser -Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet de PowerShell Get-UsUser -Identity")  

## Para mover a todos los usuarios al mismo tiempo mediante el Shell de administración de Lync Server 2013

En este ejemplo, todos los usuarios han vuelto al grupo de Office Communications Server 2007 R2 (pool01.contoso.net). Usaremos el Shell de administración de Lync Server 2013 para mover a todos los usuarios al mismo tiempo al grupo Lync Server 2013 (pool02.contoso.net).

1.  Abra el **Shell de administración de Lync Server 2013**.

2.  En la línea de comandos, escriba:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de ejemplo para mover todos los usuarios heredados en un grupo](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet de ejemplo para mover todos los usuarios heredados en un grupo")  

3.  A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  Ahora, la identidad **Grupo de registradores** de cada usuario apunta al grupo que especificó como “pool\_FQDN” en el paso anterior. La presencia de esta identidad confirma que el usuario se ha movido correctamente.

5.  Además, podemos ver la lista de usuarios en el Panel de control de Lync Server 2013 y comprobar que el valor de Grupo de registradores ahora apunta al grupo de Lync Server 2013.
    
    ![Lista de usuarios en el Panel de control de Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios en el Panel de control de Lync Server 2013")

