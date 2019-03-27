---
title: Mover un usuario único para el grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede mover un usuario de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019. En el ejemplo siguiente, en la columna grupo de registrador, pool01.contoso.net es el grupo heredado y todos los seis de estos usuarios están conectados a este grupo de servidores. Use los siguientes procedimientos para mover un usuario a su Skype para grupo de negocio Server 2019 mediante Skype para el Panel de Control de Business Server 2019 y Skype para Shell de administración de servidor empresarial.
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880252"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover un usuario único para el grupo piloto

Puede mover un usuario de su grupo heredado a su Skype para Business Server 2019 grupo piloto con Skype para el Panel de Control de Business Server 2019 o Skype para Shell de administración de Business Server 2019. En el ejemplo siguiente, en la columna **grupo de registrador** , **pool01.contoso.net** es el grupo heredado y todos los seis de estos usuarios están conectados a este grupo de servidores. Use los siguientes procedimientos para mover un usuario a su Skype para grupo de negocio Server 2019 mediante Skype para el Panel de Control de Business Server 2019 y Skype para Shell de administración de servidor empresarial. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover un usuario mediante el Skype para el Panel de Control de Business Server 2019
  
1. Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.
    
2. Abra **Skype para el Panel de Control de servidor empresarial**.
    
3. Haga clic en **usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Buscar**.
    
4. Seleccione el usuario que desea mover a la Skype para el grupo de servidores de Business Server 2019. En este ejemplo, moveremos a Sara Davis.
    
5. En el menú **Acción**, seleccione **Mover usuarios seleccionados a grupo**.
    
6. En la lista desplegable, seleccione el Skype para el grupo de servidores de Business Server 2019.
    
7. Haga clic en **acción**y, a continuación, haga clic en **mover usuarios seleccionados al grupo de servidores**. Haga clic en **Aceptar**.
  
8. Compruebe que la columna **grupo de registrador** para el usuario contiene ahora el Skype para el grupo de Business Server 2019, que indica que el usuario se ha movido correctamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover un usuario mediante el Skype para Shell de administración de Business Server 2019

1. Abra el Skype para Shell de administración de servidor empresarial.
    
2. En la línea de comandos, escriba: 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. A continuación, en la línea de comandos, escriba lo siguiente: 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. La identidad de **RegistrarPool** ahora apunta a la Skype para el grupo de servidores de Business Server 2019. La presencia de esta identidad confirma que el usuario se ha movido correctamente. 

    > [!NOTE]
    > Para obtener información detallada acerca del cmdlet **Get-CsUser** , ejecute: **Get-Help Get-CsUser-detallada**
  

