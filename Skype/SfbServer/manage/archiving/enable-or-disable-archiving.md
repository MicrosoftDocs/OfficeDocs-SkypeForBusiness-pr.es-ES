---
title: Habilitar o deshabilitar el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: Conozca cómo habilitar o deshabilitar el archivado en Skype para Business Server 2015.'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a>Habilitar o deshabilitar el archivado en Skype Empresarial Server 2015

**Resumen:** Obtenga información acerca de cómo habilitar o deshabilitar el archivado en Skype para Business Server 2015.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar o deshabilitar el archivado con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para la configuración, haga clic en **Deshabilitar archivado**.
    
5. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar o deshabilitar el archivado con Windows PowerShell

También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration**. Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado de manera que solo se archivan las sesiones de mensajería instantánea. El comando llama el cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todos los valores de configuración de archiving actualmente en uso en la organización. Esta colección, a continuación, se canaliza hacia el cmdlet **Where-Object** , que selecciona únicamente los valores que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf". A continuación, la colección filtrada se canaliza hacia el cmdlet **Set-CsArchivingConfiguration** , que toma cada elemento de la colección y cambia el valor de EnableArchiving a "ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```