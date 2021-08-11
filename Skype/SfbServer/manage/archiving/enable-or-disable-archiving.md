---
title: Habilitar o deshabilitar el archivado en Skype Empresarial Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype Empresarial Server.'
ms.openlocfilehash: 83ed391ed482d3bd744e963e1589726729a52b6e3f1c65a776b213a809eabed4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283382"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar o deshabilitar el archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype Empresarial Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar o deshabilitar el archivado mediante el Panel de control

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
   - Para habilitar el archivado solamente para las sesiones de MI, haga clic en **Archivar sesiones de mensajería instantánea**.
    
   - Para habilitar el archivado para las sesiones de mensajería instantánea y para las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para la configuración, haga clic **en Deshabilitar archivado.**
    
5. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar o deshabilitar el archivado mediante Windows PowerShell

También puede habilitar o deshabilitar el archivado mediante el cmdlet **Set-CsArchivingConfiguration.** Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado para que solo se archiven las sesiones de mensajería instantánea. El comando llama al cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todas las opciones de configuración de archivado que se usan actualmente en la organización. A continuación, esta colección se canaliza al cmdlet **Where-Object,** que selecciona solo aquellas configuraciones en las que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf". A continuación, la colección filtrada se canaliza al cmdlet **Set-CsArchivingConfiguration,** que toma cada elemento de la colección y cambia el valor de EnableArchiving a "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
