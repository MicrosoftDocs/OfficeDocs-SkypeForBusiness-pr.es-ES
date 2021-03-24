---
title: Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: obtenga información sobre cómo asignar una directiva de archivado a los usuarios de Skype Empresarial Server.'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095494"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo asignar una directiva de archivado a los usuarios de Skype Empresarial Server.
  
Si ha creado una o varias directivas de usuario para el archivado para usuarios que se aloban en Skype Empresarial Server, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas adecuadas a esos usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla al menos a un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Skype Empresarial Server del usuario.
  
> [!NOTE]
> Si ha habilitado la integración de Microsoft Exchange para la implementación, las directivas de retención de Exchange In-Place controlan si el archivado está habilitado para los usuarios que se encuentran en Exchange y tienen sus buzones en espera In-Place espera. Para obtener más información, vea [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) y Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar una directiva de usuario mediante el Panel de control

Para aplicar una directiva de usuario mediante el Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar. 
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server en** Directiva de **archivado,** seleccione la directiva de usuario de archivado que desea aplicar.
    
    > [!NOTE]
    > La **\<Automatic\>** configuración aplica la configuración predeterminada de instalación del servidor. Esta configuración se aplica automáticamente por el servidor.
  
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar una directiva de usuario mediante Windows PowerShell

También puede aplicar una directiva de usuario mediante el Windows PowerShell **cmdlet Grant-CsArchivingPolicy.**
  
El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Este comando asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tienen cuentas en el grupo de registradores atl-cs-001.contoso.com. Para obtener más información sobre el parámetro Filter usado en este comando, consulte la documentación del cmdlet [Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

El siguiente comando quita cualquier directiva de archivado por usuario asignada anteriormente a Ken Myer. Después de quitar la directiva por usuario, Ken Myer se administrará automáticamente mediante la directiva global o, si existe, su directiva de sitio local. Las directivas de sitio tienen prioridad sobre la directiva global.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
