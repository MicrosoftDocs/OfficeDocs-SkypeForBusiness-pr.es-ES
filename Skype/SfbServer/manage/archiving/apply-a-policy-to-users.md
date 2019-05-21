---
title: Aplicar una directiva de archivado a los usuarios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: Aprenda a asignar una directiva de archivado a los usuarios en Skype empresarial Server.'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282052"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Aplicar una directiva de archivado a los usuarios en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo asignar una directiva de archivado a los usuarios en Skype empresarial Server.
  
Si ha creado una o más directivas de usuario para archivar para usuarios alojados en Skype empresarial Server, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas apropiadas a esos usuarios o grupos de usuarios. Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla a al menos un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Skype empresarial Server del usuario.
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange y si sus buzones se colocan en la retención local. Para obtener más información, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) y [configurar la integración con el almacenamiento de Exchange para Skype empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar una directiva de usuario con el Panel de control

Para aplicar una directiva de usuario con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar. 
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** , en **Directiva**de archivado, seleccione la Directiva de usuario de archivado que desea aplicar.
    
    > [!NOTE]
    > La ** \<configuración\> automática** aplica la configuración predeterminada de la instalación del servidor. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar una directiva de usuario mediante Windows PowerShell

También puede aplicar una directiva de usuario mediante el cmdlet **Grant-CsArchivingPolicy de** Windows PowerShell.
  
El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Con este comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas hospedadas en el grupo de registradores atl-cs-001.contoso.com. Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

El siguiente comando quita cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez quitada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado con la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre las directivas globales.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

