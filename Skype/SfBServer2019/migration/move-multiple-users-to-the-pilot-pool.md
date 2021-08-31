---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Puede mover varios usuarios del grupo heredado al grupo piloto de Skype Empresarial Server 201 Skype Empresarial Server 9 mediante el Panel de control de 2019 o el Shell de administración de Skype Empresarial Server 2019.
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726319"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios al grupo piloto

Puede mover varios usuarios del grupo heredado al grupo piloto de Skype Empresarial Server 201 Skype Empresarial Server 9 mediante el Panel de control de 2019 o el Shell de administración de Skype Empresarial Server 2019.

 **En este artículo**
  
[Para mover varios usuarios mediante el Panel de control Skype Empresarial Server 2019](#sectionSection0)
  
[Para mover varios usuarios mediante el Shell de Skype Empresarial Server 2019](#sectionSection1)
  
[Para mover todos los usuarios al mismo tiempo mediante el Shell de administración Skype Empresarial Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover varios usuarios mediante el Panel de control Skype Empresarial Server 2019
<a name="sectionSection0"> </a>

1. Abra Skype Empresarial Server Panel de control.
    
2. Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.
    
3. Seleccione dos usuarios que desea mover al grupo Skype Empresarial Server 2019. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
     ![Mover usuarios a un grupo de registros específico.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.
    
5. En la lista desplegable, seleccione el grupo Skype Empresarial Server 2019.
    
6. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
     ![Cuadro de diálogo Mover usuarios, grupo de registradores de destino.](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Compruebe que la **columna Grupo de** registradores para los usuarios ahora contiene el grupo de servidores Skype Empresarial Server 2019, lo que indica que los usuarios se han movido correctamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover varios usuarios mediante el Shell de Skype Empresarial Server 2019
<a name="sectionSection1"> </a>

1. Abra el shell Skype Empresarial Server administración de 2019. 
    
2. En la línea de comandos, escriba lo siguiente y reemplace **User1** y **User2** por nombres de usuario específicos que desee mover y reemplace **pool_FQDN** por el nombre del grupo de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan: 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet Get-CsUser PowerShell.](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Escriba lo siguiente en la línea de comandos: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que **user2** se ha movido. 
    
     ![Salida del cmdlet Get-UsUser -Identity de PowerShell.](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el Shell de administración Skype Empresarial Server 2019
<a name="sectionSection2"> </a>

En este ejemplo, todos los usuarios se han devuelto al grupo heredado (pool01.contoso.net). Con el Shell Skype Empresarial Server administración de 2019, moveremos todos los usuarios al mismo tiempo al grupo de servidores de Skype Empresarial Server 2019 (pool02.contoso.net).
  
1. Abra el shell Skype Empresarial Server administración de 2019.
    
2. Escriba lo siguiente en la línea de comandos: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en shell de administración.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Ejecute **Get-CsUser** para uno de los usuarios piloto. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. La **identidad del grupo de** registradores para cada usuario ahora apunta al grupo que especificó como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que se movió al usuario correctamente. 
    
5. Además, podemos ver la lista de usuarios en el Panel de control de Skype Empresarial Server 2019 y comprobar que el valor del grupo de registradores ahora apunta al grupo de servidores Skype Empresarial Server 2019.
    
     ![Skype Empresarial Server de usuarios del Panel de control de 2019.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

