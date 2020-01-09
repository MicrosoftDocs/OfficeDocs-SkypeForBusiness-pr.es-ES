---
title: Eliminar una configuración de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumen: Aprenda a eliminar una configuración de archivado en Skype empresarial Server.'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992377"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Eliminar una configuración de archivado en Skype empresarial Server

**Resumen:** Aprenda a eliminar una configuración de archivado en Skype empresarial Server.
  
Es posible eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Eliminar la configuración de archivado con el Panel de control

Para eliminar la configuración de archivado con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, luego, haga clic en **Editar** y en **Eliminar**.
    
    > [!NOTE]
    > También puede hacer clic en la configuración global, pero seleccione esta opción solo si desea restablecer la configuración global a los valores predeterminados. 
  
5. Haga clic en **Confirmar**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Eliminar una configuración de archivado con Windows PowerShell

También puede eliminar una configuración de archivado mediante el cmdlet **Remove-CsArchivingConfiguration** .
  
Por ejemplo, el siguiente comando quita las opciones de configuración del archivado aplicadas al sitio de Redmond. Cuando se elimina una directiva configurada en el ámbito de sitio, los usuarios a los que anteriormente administraba esta directiva de sitio se regirán de forma automática por la directiva de archivado global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

El siguiente comando quita todas las opciones de configuración de archivado en las que se deshabilitó el archivado de Exchange:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

También puede usar el cmdlet **Remove-CsArchivingConfiguration** para restablecer la configuración global a los valores predeterminados. Por ejemplo, si ha habilitado el archivado de las sesiones de mensajería instantánea de forma global, el siguiente comando restablecerá el valor al valor Ninguno predeterminado, y así se deshabilitará el archivado de manera global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
