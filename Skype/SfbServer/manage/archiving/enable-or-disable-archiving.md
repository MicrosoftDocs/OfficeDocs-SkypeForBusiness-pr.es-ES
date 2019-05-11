---
title: Habilitar o deshabilitar el archivado en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype para Business Server.'
ms.openlocfilehash: 27cb7aab08c6a85f21e058848963bb42de6e1635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885034"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar o deshabilitar el archivado en Skype para Business Server

**Resumen:** Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype para Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar o deshabilitar el archivado con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para la configuración, haga clic en **Deshabilitar archivado**.
    
5. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar o deshabilitar el archivado con Windows PowerShell

También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration**. Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado de manera que solo se archivan las sesiones de mensajería instantánea. El comando llama al cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todas las opciones de configuración de archivado que se están utilizando en la organización. A continuación, esa recopilación se canaliza al cmdlet **Where-Object**, que selecciona únicamente las opciones en las que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf". Luego, la recopilación filtrada se canaliza al cmdlet **Set-CsArchivingConfiguration**, que toma cada elemento en la colección y cambia el valor de EnableArchiving a "ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
