---
title: Mover un único usuario al grupo piloto
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
description: Puede mover un usuario de su grupo heredado a su grupo piloto de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 o el Shell de administración de Skype Empresarial Server 2019. En el siguiente ejemplo, en la columna grupo de registradores, pool01.contoso.net es el grupo heredado y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario a su grupo de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 y el Shell de administración de Skype Empresarial Server.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752512"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un único usuario al grupo piloto

Puede mover un usuario de su grupo heredado a su grupo piloto de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 o el Shell de administración de Skype Empresarial Server 2019. En el siguiente ejemplo, en la columna **Grupo** de registradores, **pool01.contoso.net** es el grupo heredado y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario a su grupo de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server 2019 y el Shell de administración de Skype Empresarial Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover un usuario mediante el Panel de control de Skype Empresarial Server 2019
  
1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra **el Panel de control de Skype Empresarial Server.**
    
3. Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.
    
4. Seleccione un usuario que desee mover al grupo de Skype Empresarial Server 2019. En ste ejemplo, moveremos al usuario Sara Davis.
    
5. En el menú  **Acción**, haga clic en  **Mover usuarios seleccionados a un grupo de servidores**.
    
6. En la lista desplegable, seleccione el grupo de Skype Empresarial Server 2019.
    
7. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
  
8. Compruebe que la **columna del grupo** de registradores para el usuario ahora contiene el grupo de Skype Empresarial Server 2019, que indica que el usuario se ha movido correctamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover un usuario mediante el Shell de administración de Skype Empresarial Server 2019

1. Abra el Shell de administración de Skype Empresarial Server.
    
2. En la línea de comandos, escriba lo siguiente: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. A continuación, en la línea de comandos, escriba lo siguiente: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. La **identidad RegistrarPool** ahora apunta al grupo de Skype Empresarial Server 2019. La presencia de esta identidad confirma que se movió al usuario correctamente. 

    > [!NOTE]
    > Para obtener más información sobre el cmdlet **Get-CsUser,** ejecute: **Get-Help Get-CsUser -Detailed**
  

