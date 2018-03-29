---
title: Configurar las opciones de archivado para gestionar las fallas en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumen: Conozca cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype Error 2015 de servidor empresariales que impedirían que el archiving.'
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a>Configurar las opciones de archivado para gestionar las fallas en Skype Empresarial Server 2015

**Resumen:** Obtenga información sobre cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype Error 2015 de servidor empresariales que impedirían que el archiving.
  
Si el archivado es un requisito para su organización, puede bloquear sesiones de mensajería instantánea y conferencias en caso de un Skype error Business Server que podrían impedir el archivado. A veces se denomina modo crítico. Por ejemplo, si existe un problema con un servicio de almacenamiento, la mensajería instantánea se bloquearía para los usuarios cuyas comunicaciones están habilitadas para el archivado. Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrijan los errores. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar el modo crítico con el Panel de control

Para especificar si las sesiones de comunicación se tienen que permitir en caso de un error que no permita el archivado:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y luego haga clic en **Mostrar detalles**.
    
5. Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.
    
6. Haga clic en **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar el modo crítico con Windows PowerShell

También puede especificar si se deben permitir las sesiones de comunicación en caso de errores que podrían impedir el archivado mediante el cmdlet **Set-CsArchivingConfiguration** con el parámetro BlockOnArchiveFailure.
  
Por ejemplo, el siguiente comando deshabilita la comunicación en el caso de un error de archivado:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

El siguiente comando habilita las comunicaciones en caso de un error de archivado:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

