---
title: Aplicar una directiva de archivado para los usuarios de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: Obtenga información sobre cómo asignar una directiva de archivado para los usuarios de Skype para Business Server.'
ms.openlocfilehash: bc54c25a710e4e1cca44fb7311a47101f31ef7df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985619"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Aplicar una directiva de archivado para los usuarios de Skype para Business Server

**Resumen:** Obtenga información sobre cómo asignar una directiva de archivado para los usuarios de Skype para Business Server.
  
Si ha creado uno o más directivas de usuario para el archivado para los usuarios alojados en Skype para Business Server, puede implementar la compatibilidad con el archivado para usuarios específicos mediante la aplicación de las directivas apropiadas para los usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicar al menos un usuario o grupo de usuarios que admita el archivado de Skype del usuario para las comunicaciones de servidor empresarial.
  
> [!NOTE]
> Si se habilita la integración de Microsoft Exchange para la implementación, el control de las directivas de retención de Exchange local si el archivado está habilitado para los usuarios que están ubicados en Exchange y disponer sus buzones en suspensión en contexto. Para obtener información detallada, vea [Planear el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) y [Configure la integración con el almacenamiento de Exchange de Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar una directiva de usuario con el Panel de control

Para aplicar una directiva de usuario con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar. 
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la directiva de usuario de archivado que desea aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la configuración predeterminada de la instalación de servidor. El servidor aplica esta configuración automáticamente.
  
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar una directiva de usuario mediante Windows PowerShell

También puede aplicar una directiva de usuario mediante el cmdlet de Windows PowerShell **Grant-CsArchivingPolicy** .
  
El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Con este comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas hospedadas en el grupo de registradores atl-cs-001.contoso.com. Para obtener información detallada sobre el parámetro de filtro que se usa en este comando, vea la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

El siguiente comando quita cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez quitada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado con la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre las directivas globales.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obtener información detallada, vea la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

