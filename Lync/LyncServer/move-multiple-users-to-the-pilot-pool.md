---
title: Mover múltiples usuarios al grupo piloto
TOCTitle: Mover múltiples usuarios al grupo piloto
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48276020
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover múltiples usuarios al grupo piloto

 

_**Última modificación del tema:** 2012-10-02_

Puede mover varios usuarios de su grupo de Lync Server 2010 al grupo piloto de Lync Server 2013 mediante Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para mover varios usuarios mediante el Panel de control de Lync Server 2013

1.  Abrir **Panel de control de Lync Server** .

2.  Haga clic en **Usuarios** , haga clic en Buscar y, a continuación, haga clic en **Encontrar** .

3.  Seleccione los dos usuarios que quiera mover al grupo de Lync Server 2013. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
    ![Mover usuarios a un grupo de registradores específico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuarios a un grupo de registradores específico")  

4.  En el menú **Acción** , seleccione **Mover usuarios seleccionados a grupo** .

5.  En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.

6.  Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo** . Haga clic en Aceptar.
    
    ![Mover usuarios, cuadro de diálogo de grupo de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Mover usuarios, cuadro de diálogo de grupo de registradores de destino")  

7.  Compruebe que la columna **Grupo de registradores** de los usuarios ahora contiene el grupo Lync Server 2013, lo que indica que se ha movido correctamente a los usuarios.

## Para mover varios usuarios mediante el Shell de administración de Lync Server 2013

1.  Abra Shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba lo siguiente y sustituya **User1** y **User2** por los nombres de usuario concretos que quiere mover, y sustituya **pool\_FQDN** por el nombre del grupo de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan:
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Ejemplo del cmdlet de PowerShell Get-CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Ejemplo del cmdlet de PowerShell Get-CsUser")  

3.  En la línea de comandos, escriba lo siguiente
    
        Get-CsUser -Identity "User1"

4.  Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool\_FQDN** en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que se ha movido a **User2**.
    
    ![Resultado del cmdlet de PowerShell Get-UsUser -Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Resultado del cmdlet de PowerShell Get-UsUser -Identity")  

## Para mover a todos los usuarios al mismo tiempo mediante el Shell de administración de Lync Server 2013

En este ejemplo, todos los usuarios han vuelto al grupo de Lync Server 2010 (pool01.contoso.net). Usaremos el Shell de administración de Lync Server 2013 para mover a todos los usuarios al mismo tiempo al grupo Lync Server 2013 (pool02.contoso.net).

1.  Abra el **Shell de administración de Lync Server 2013**.

2.  En la línea de comandos, escriba:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet de PowerShell y resultados en el Shell de administración](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet de PowerShell y resultados en el Shell de administración")  

3.  A continuación, ejecute **Get-CsUser** para uno de los usuarios piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  Ahora, la identidad **Grupo de registradores** de cada usuario apunta al grupo que especificó como “pool\_FQDN” en el paso anterior. La presencia de esta identidad confirma que el usuario se ha movido correctamente.

5.  Además, podemos ver la lista de usuarios en el Panel de control de Lync Server 2013 y comprobar que el valor de Grupo de registradores ahora apunta al grupo de Lync Server 2013.
    
    ![Lista de usuarios en el Panel de control de Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuarios en el Panel de control de Lync Server 2013")

