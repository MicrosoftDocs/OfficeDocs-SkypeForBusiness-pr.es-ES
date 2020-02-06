---
title: Configurar opciones de archivado para controlar errores en Skype empresarial Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumen: Aprenda a bloquear las sesiones de mensajería instantánea y de conferencia en caso de que se produzca un error de Skype empresarial Server que impida el archivado.'
ms.openlocfilehash: c1a6b9930d9f27e9d679710708141c0394c41dc4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818972"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opciones de archivado para controlar errores en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo bloquear las sesiones de mensajería instantánea y conferencias en caso de que se produzca un error de Skype empresarial Server que impida el archivado.
  
Si el archivado es un requisito para su organización, puede bloquear las sesiones de mensajería instantánea y de conferencias en el caso de que se produzca un error de Skype empresarial Server que impida el archivado. A veces se denomina modo crítico. Por ejemplo, si existe un problema con un servicio de almacenamiento, la mensajería instantánea se bloquearía para los usuarios cuyas comunicaciones están habilitadas para el archivado. Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrijan los errores. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar el modo crítico con el Panel de control

Para especificar si las sesiones de comunicación se tienen que permitir en caso de un error que no permita el archivado:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y luego haga clic en **Mostrar detalles**.
    
5. Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.
    
6. Haga clic en **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar el modo crítico con Windows PowerShell

También puede especificar si se deben permitir las sesiones de comunicación en caso de que se produzca un error que impida el archivado mediante el cmdlet **set-CsArchivingConfiguration** con el parámetro BlockOnArchiveFailure.
  
Por ejemplo, el siguiente comando deshabilita las comunicaciones en caso de que se produzca un error de archivado:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

El siguiente comando habilita las comunicaciones en caso de un error de archivado:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

