---
title: Habilitar o deshabilitar el archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: Aprenda a habilitar o deshabilitar el archivado en Skype empresarial Server.'
ms.openlocfilehash: 0e4ef4dde27ffa5856f2b73b69ffbadc24399c59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286147"
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
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
