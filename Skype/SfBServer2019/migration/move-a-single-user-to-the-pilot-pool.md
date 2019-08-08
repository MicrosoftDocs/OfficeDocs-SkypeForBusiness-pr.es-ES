---
title: Mover un solo usuario a la agrupación piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019. En el ejemplo siguiente, en la columna registrar grupo, pool01.contoso.net es el grupo heredado y los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server.
ms.openlocfilehash: 456035cfd917f620383d4dff70f6366cd73d530e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237768"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un solo usuario a la agrupación piloto

Puede mover un usuario de su grupo heredado a su grupo piloto de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server 2019 o el shell de administración de Skype empresarial 2019. En el ejemplo siguiente, en la columna **registrar grupo** , **pool01.contoso.net** es el grupo heredado y los seis de estos usuarios están conectados a este grupo. Use los procedimientos siguientes para mover un usuario a su grupo de servidores de Skype empresarial 2019 con el panel de control de Skype empresarial Server 2019 y el shell de administración de Skype empresarial Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover un usuario mediante el panel de control de Skype empresarial Server 2019
  
1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra el **Panel de control de Skype empresarial Server**.
    
3. Haga clic en **usuarios**, en **Buscar**y, a continuación, en **Buscar**.
    
4. Seleccione el usuario que desea mover al grupo de servidores de Skype empresarial 2019. En este ejemplo, moveremos a Sara Davis.
    
5. En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.
    
6. En la lista desplegable, seleccione el grupo de servidores de Skype empresarial 2019.
    
7. Haga clic en **acción**y, a continuación, haga clic en **mover los usuarios seleccionados al grupo**. Haga clic en **Aceptar**.
  
8. Compruebe que la columna del **Grupo registrador** del usuario contiene ahora el grupo de servidores de Skype empresarial 2019, lo que indica que el usuario se ha movido correctamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover un usuario mediante el shell de administración de Skype empresarial Server 2019

1. Abra el shell de administración de Skype empresarial Server.
    
2. En la línea de comandos, escriba: 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. A continuación, en la línea de comandos, escriba lo siguiente: 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. La identidad de **RegistrarPool** apunta ahora al grupo de servidores de Skype empresarial 2019. La presencia de esta identidad confirma que el usuario se movió correctamente. 

    > [!NOTE]
    > Para obtener detalles sobre el cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-** Detailed
  

