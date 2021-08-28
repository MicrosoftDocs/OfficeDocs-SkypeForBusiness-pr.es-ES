---
title: Eliminar una configuración de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumen: obtenga información sobre cómo eliminar una configuración de archivado en Skype Empresarial Server.'
ms.openlocfilehash: 046bd2c1fc5e54189ac038bdf769a711b3c9a774
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621146"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Eliminar una configuración de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo eliminar una configuración de archivado en Skype Empresarial Server.
  
Puede eliminar una configuración de sitio o una configuración de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Eliminar una configuración de archivado mediante el Panel de control

Para eliminar una configuración de archivado mediante el Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, después, haga clic en **Editar** y en **Eliminar**.
    
    > [!NOTE]
    > También puede hacer clic en la configuración global, pero elija esta opción solo si desea restablecer la configuración global a los valores predeterminados. 
  
5. Haga clic en **Confirmar**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Eliminar una configuración de archivado mediante Windows PowerShell

También puede eliminar una configuración de archivado mediante el cmdlet **Remove-CsArchivingConfiguration.**
  
Por ejemplo, el siguiente comando quita las opciones de configuración de archivado aplicadas al sitio redmond. Cuando se elimina una directiva configurada en el ámbito del sitio, los usuarios administrados anteriormente por la directiva de sitio se regirán automáticamente por la directiva de archivado global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

El siguiente comando quita todas las opciones de configuración de archivado Exchange se ha deshabilitado el archivado:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

También puede usar el cmdlet **Remove-CsArchivingConfiguration** para restablecer la configuración global a los valores predeterminados. Por ejemplo, supongamos que ha habilitado el archivado de sesiones de mensajería instantánea en el nivel global; el siguiente comando restablecerá el valor predeterminado de None, que deshabilitará el archivado en el nivel global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsArchivingConfiguration.](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)