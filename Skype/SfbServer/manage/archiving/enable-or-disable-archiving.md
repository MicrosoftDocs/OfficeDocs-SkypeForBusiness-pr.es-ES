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
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817600"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar o deshabilitar el archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype Empresarial Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar o deshabilitar el archivado mediante el Panel de control

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
   - Para habilitar el archivado solamente para las sesiones de MI, haga clic en **Archivar sesiones de mensajería instantánea**.
    
   - Para habilitar el archivado para las sesiones de mensajería instantánea y para las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para la configuración, haga clic **en Deshabilitar archivado.**
    
5. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilite o deshabilite el archivado mediante Windows PowerShell

También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration.** Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado para que solo se archiven las sesiones de mensajería instantánea. El comando llama al cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todas las opciones de configuración de archivado actualmente en uso en la organización. A continuación, esta colección se canaliza al cmdlet **Where-Object,** que selecciona solo las configuraciones en las que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf". A continuación, la recopilación filtrada se canaliza al cmdlet **Set-CsArchivingConfiguration,** que toma cada elemento de la colección y cambia el valor de EnableArchiving a "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
