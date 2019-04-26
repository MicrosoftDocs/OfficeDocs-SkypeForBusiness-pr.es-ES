---
title: Mover varios usuarios al grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover varios usuarios de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019.
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233970"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover varios usuarios al grupo piloto

Puede mover varios usuarios de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019.

 **En este artículo**
  
[Para mover varios usuarios mediante el Skype para el Panel de Control de Business Server 2019](#sectionSection0)
  
[Para mover varios usuarios mediante el Skype para Shell de administración de Business Server 2019](#sectionSection1)
  
[Para mover todos los usuarios al mismo tiempo mediante el Skype para Shell de administración de Business Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover varios usuarios mediante el Skype para el Panel de Control de Business Server 2019
<a name="sectionSection0"> </a>

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. Haga clic en **usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Buscar**.
    
3. Seleccione dos usuarios que se desean mover a la Skype para el grupo de servidores de Business Server 2019. En este ejemplo, se va a mover los usuarios Chen Bermejo y Claus Hansen.
    
     ![Mover usuarios al grupo de registro específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. En el menú **acción** , seleccione **mover usuarios seleccionados al grupo de servidores**.
    
5. En la lista desplegable, seleccione el Skype para el grupo de servidores de Business Server 2019.
    
6. Haga clic en **acción**y, a continuación, haga clic en **mover usuarios seleccionados al grupo de servidores**. Haga clic en **Aceptar**.
    
     ![Mover usuarios, cuadro de diálogo de grupo de servidores de registrador de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Compruebe que la columna **grupo de registrador** para los usuarios ahora contiene el Skype para el grupo de Business Server 2019, que indica que los usuarios se han movido correctamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover varios usuarios mediante el Skype para Shell de administración de Business Server 2019
<a name="sectionSection1"> </a>

1. Abra el Skype para Shell de administración de Business Server 2019. 
    
2. En la línea de comandos, escriba lo siguiente y reemplace **User1** y **User2** por nombres de usuario específicos que desea mover y sustituya **pool_FQDN** por el nombre del grupo de servidores de destino. En este ejemplo se va a mover los usuarios Hao Chen y Katie Jordan. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Ejemplo de cmdlet de PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. En la línea de comandos, escriba: 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. La identidad **Del grupo de registrador** ahora debe apuntar al grupo de servidores especificado como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que el usuario se ha movido correctamente. Repita el paso para comprobar que se ha movido **el usuario 2** . 
    
     ![Salida de PowerShell Get-UsUser-cmdlet de identidad](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos los usuarios al mismo tiempo mediante el Skype para Shell de administración de Business Server 2019
<a name="sectionSection2"> </a>

En este ejemplo, se han devuelto todos los usuarios al grupo de servidores heredado (pool01.contoso.net). Usa el Skype para Shell de administración de Business Server 2019, se va a mover todos los usuarios al mismo tiempo a la Skype para el grupo de servidores de Business Server 2019 (pool02.contoso.net).
  
1. Abra el Skype para Shell de administración de Business Server 2019.
    
2. En la línea de comandos, escriba: 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet de PowerShell y los resultados en el Shell de administración](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Ejecute **Get-CsUser** para uno de los usuarios pilotos. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. La identidad del **Grupo de registrador** para cada usuario ahora apunta al grupo de servidores especificado como **pool_FQDN** en el paso anterior. La presencia de esta identidad confirma que el usuario se ha movido correctamente. 
    
5. Además, podemos ver la lista de usuarios en el Skype para el Panel de Control de Business Server 2019 y compruebe que el valor de grupo de registradores ahora apunta a la Skype para el grupo de servidores de Business Server 2019.
    
     ![Skype para la lista de usuario del Panel de Control de Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

