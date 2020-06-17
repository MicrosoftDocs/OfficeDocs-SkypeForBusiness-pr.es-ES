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
localization_priority: Normal
description: Puede mover varios usuarios de su grupo heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753432"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios al grupo piloto

Puede mover varios usuarios de su grupo heredado al grupo piloto de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial Server 2019.

 **En este artículo**
  
[Para mover varios usuarios mediante el panel de control de Skype empresarial Server 2019](#sectionSection0)
  
[Para mover varios usuarios mediante el shell de administración de Skype empresarial Server 2019](#sectionSection1)
  
[Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Skype empresarial Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover varios usuarios mediante el panel de control de Skype empresarial Server 2019
<a name="sectionSection0"> </a>

1. Abra el panel de control de Skype empresarial Server.
    
2. Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.
    
3. Seleccione dos usuarios que quiera mover al grupo de Skype empresarial Server 2019. En este ejemplo, moveremos los usuarios Chen Yang y Claus Hansen.
    
     ![Mover usuarios a un grupo de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. En el menú **Acción** seleccione **Mover usuarios seleccionados a grupo**.
    
5. En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.
    
6. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
    
     ![Cuadro de diálogo mover usuarios, grupo de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Compruebe que la columna **grupo de registradores** para los usuarios contiene ahora el grupo de servidores de Skype empresarial Server 2019, que indica que los usuarios se han movido correctamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover varios usuarios mediante el shell de administración de Skype empresarial Server 2019
<a name="sectionSection1"> </a>

1. Abra el shell de administración de Skype empresarial Server 2019. 
    
2. En la línea de comandos, escriba lo siguiente y reemplace **user1** y **user2** por los nombres de usuario específicos que desea mover, y reemplace **pool_FQDN** por el nombre del grupo de servidores de destino. En este ejemplo, moveremos los usuarios Hao Chen y Katie Jordan: 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet Get-CsUser de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Escriba lo siguiente en la línea de comandos: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Ahora, la identidad **Grupo de registradores** debería apuntar al grupo que especificó como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que se ha movido correctamente al usuario. Repita el paso para comprobar que se ha movido a **usuario2** . 
    
     ![Resultado del cmdlet PowerShell Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el shell de administración de Skype empresarial Server 2019
<a name="sectionSection2"> </a>

En este ejemplo, todos los usuarios se han devuelto al grupo heredado (pool01.contoso.net). Con el shell de administración de Skype empresarial Server 2019, todos los usuarios se moverán al mismo tiempo al grupo de servidores de Skype empresarial 2019 (pool02.contoso.net).
  
1. Abra el shell de administración de Skype empresarial Server 2019.
    
2. Escriba lo siguiente en la línea de comandos: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en Shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Ejecute **Get-CsUser** para uno de los usuarios piloto. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. La identidad del **grupo de registradores** para cada usuario apunta ahora al grupo especificado como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que se movió al usuario correctamente. 
    
5. Además, podemos ver la lista de usuarios en el panel de control de Skype empresarial Server 2019 y comprobar que el valor del grupo de registradores ahora apunta al grupo de Skype empresarial Server 2019.
    
     ![Lista de usuarios del panel de control de Skype empresarial Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

