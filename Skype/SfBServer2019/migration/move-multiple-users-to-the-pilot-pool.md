---
title: Mover varios usuarios a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover varios usuarios de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.
ms.openlocfilehash: 3798525145776c61eed6b1dabebe657538d7c9db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282227"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios a la agrupación piloto

Puede mover varios usuarios de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019.

 **En este artículo**
  
[Para mover varios usuarios con el panel de control de Skype empresarial Server 2019](#sectionSection0)
  
[Para mover varios usuarios con el shell de administración de Skype empresarial Server 2019](#sectionSection1)
  
[Para mover todos los usuarios al mismo tiempo con el shell de administración de Skype empresarial Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover varios usuarios con el panel de control de Skype empresarial Server 2019
<a name="sectionSection0"> </a>

1. Abra el panel de control de Skype empresarial Server.
    
2. Haga clic en **usuarios**, en **Buscar**y, a continuación, en **Buscar**.
    
3. Seleccione dos usuarios que quiera mover al grupo de servidores de Skype empresarial 2019. En este ejemplo, se moverán los usuarios Chen Yang y Claus Hansen.
    
     ![Mover usuarios a un grupo de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. En el menú **acción** , seleccione **mover usuarios seleccionados al grupo**.
    
5. En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.
    
6. Haga clic en **acción**y, a continuación, haga clic en **mover los usuarios seleccionados al grupo**. Haga clic en **Aceptar**.
    
     ![Cuadro de diálogo mover usuarios, conjunto de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Compruebe que la columna del **Grupo registrador** de los usuarios contiene ahora el grupo de servidores de Skype empresarial 2019, lo que indica que los usuarios se movieron correctamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover varios usuarios con el shell de administración de Skype empresarial Server 2019
<a name="sectionSection1"> </a>

1. Abra el shell de administración de Skype empresarial Server 2019. 
    
2. En la línea de comandos, escriba lo siguiente y sustituya el **usuario1** y el **usuario2** por los nombres de usuario específicos que desea mover y sustituya **pool_FQDN** por el nombre del grupo de destino. En este ejemplo, moveremos a los usuarios Hao Chen y Katie Katie. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet Get-CsUser de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. En la línea de comandos, escriba: 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. La identidad del **Grupo** de registradores debe apuntar ahora al grupo que especificó como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que el usuario se movió correctamente. Repita el paso para comprobar que **usuario2** se ha movido. 
    
     ![Resultado del cmdlet Get-UsUser-Identity de PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos los usuarios al mismo tiempo con el shell de administración de Skype empresarial Server 2019
<a name="sectionSection2"> </a>

En este ejemplo, todos los usuarios han sido devueltos al grupo heredado (pool01.contoso.net). Con el shell de administración de Skype empresarial Server 2019, moveremos todos los usuarios al mismo tiempo al grupo de servidores de Skype empresarial 2019 (pool02.contoso.net).
  
1. Abra el shell de administración de Skype empresarial Server 2019.
    
2. En la línea de comandos, escriba: 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y resultados en el shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Ejecute **Get-CsUser** para uno de los usuarios de la prueba piloto. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. La identidad del **Grupo** de registradores de cada usuario apunta ahora al grupo que especificó como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que el usuario se movió correctamente. 
    
5. Además, podemos ver la lista de usuarios en el panel de control de Skype empresarial Server 2019 y verificar que el valor del grupo de registrador ahora apunta al grupo de Skype empresarial Server 2019.
    
     ![Lista de usuarios del panel de control de Skype empresarial Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

