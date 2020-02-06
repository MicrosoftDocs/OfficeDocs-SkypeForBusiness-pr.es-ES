---
title: Habilitar o deshabilitar el archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: Aprenda a habilitar o deshabilitar el archivado en Skype empresarial Server.'
ms.openlocfilehash: 8c970dba9a76abdb0c9417a5da5c7aa642fa059c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818922"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar o deshabilitar el archivado en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype empresarial Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar o deshabilitar el archivado con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para la configuración, haga clic en **Deshabilitar archivado**.
    
5. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar o deshabilitar el archivado con Windows PowerShell

También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration**. Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado de manera que solo se archivan las sesiones de mensajería instantánea. El comando llama al cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todas las opciones de configuración de archivado que se están utilizando en la organización. A continuación, esa recopilación se canaliza al cmdlet **Where-Object**, que selecciona únicamente las opciones en las que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf". Luego, la recopilación filtrada se canaliza al cmdlet **Set-CsArchivingConfiguration**, que toma cada elemento en la colección y cambia el valor de EnableArchiving a "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
