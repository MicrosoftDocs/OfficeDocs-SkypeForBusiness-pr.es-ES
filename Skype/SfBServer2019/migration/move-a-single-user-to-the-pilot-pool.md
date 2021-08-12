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
description: Puede mover un usuario de su grupo heredado al grupo piloto de Skype Empresarial Server 201 Skype Empresarial Server 9 mediante el Panel de control de 2019 o el Shell de administración de Skype Empresarial Server 2019. En el ejemplo siguiente, en la columna Grupo de registradores, pool01.contoso.net es el grupo heredado y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario al grupo de servidores de Skype Empresarial Server 2019 mediante Skype Empresarial Server Panel de control de 2019 y Skype Empresarial Server Shell de administración.
ms.openlocfilehash: 98fd1ce168cf5b44a85c1b0a93ee90634a84f885ced3cb3ffaaca8cee836a620
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303394"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un único usuario al grupo piloto

Puede mover un usuario de su grupo heredado al grupo piloto de Skype Empresarial Server 201 Skype Empresarial Server 9 mediante el Panel de control de 2019 o el Shell de administración de Skype Empresarial Server 2019. En el ejemplo siguiente, en la columna **Grupo** de registradores, **pool01.contoso.net** es el grupo heredado y los seis usuarios están conectados a este grupo. Use los siguientes procedimientos para mover un usuario al grupo de servidores de Skype Empresarial Server 2019 mediante Skype Empresarial Server Panel de control de 2019 y Skype Empresarial Server Shell de administración. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover un usuario mediante el Panel de control Skype Empresarial Server 2019
  
1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra **Skype Empresarial Server Panel de control**.
    
3. Haga clic en **Usuarios**, **Buscar** y, a continuación, en **Buscar**.
    
4. Seleccione un usuario que desee mover al grupo Skype Empresarial Server 2019. En ste ejemplo, moveremos al usuario Sara Davis.
    
5. En el menú  **Acción**, haga clic en  **Mover usuarios seleccionados a un grupo de servidores**.
    
6. En la lista desplegable, seleccione el grupo Skype Empresarial Server 2019.
    
7. Haga clic en **Acción** y, a continuación, en **Mover usuarios seleccionados a grupo**. Haga clic en **Aceptar**.
  
8. Compruebe que la **columna Grupo de** registradores del usuario ahora contiene el grupo de servidores Skype Empresarial Server 2019, lo que indica que el usuario se ha movido correctamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover un usuario mediante el Shell Skype Empresarial Server 2019

1. Abra el Shell Skype Empresarial Server administración.
    
2. En la línea de comandos, escriba lo siguiente: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. A continuación, en la línea de comandos, escriba lo siguiente: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. La **identidad de RegistrarPool** ahora apunta al grupo Skype Empresarial Server 2019. La presencia de esta identidad confirma que se movió al usuario correctamente. 

    > [!NOTE]
    > Para obtener más información sobre el cmdlet **Get-CsUser,** ejecute: **Get-Help Get-CsUser -Detailed**
  

