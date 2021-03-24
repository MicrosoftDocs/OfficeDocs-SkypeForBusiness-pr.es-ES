---
title: Configurar opciones de archivado para controlar errores en Skype Empresarial Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Summary: Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095454"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opciones de archivado para controlar errores en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo bloquear las sesiones de mensajería instantánea y conferencia en caso de un error de Skype Empresarial Server que impediría el archivado.
  
Si el archivado es un requisito para su organización, puede bloquear las sesiones de mensajería instantánea y conferencia en caso de un error de Skype Empresarial Server que impida el archivado. A veces se denomina modo crítico. Por ejemplo, si hay un problema con un servicio de almacenamiento, la mensajería instantánea se bloquearía para los usuarios cuyas comunicaciones están habilitadas para el archivado. Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar el modo crítico mediante el Panel de control

Para especificar si se deben permitir las sesiones de comunicación en caso de error que impida el archivado:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, del sitio o del grupo correspondiente en la lista de configuraciones de archivado, haga clic en **Editar** y, a continuación, haga clic **en Mostrar detalles.**
    
5. Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.
    
6. Haga clic en **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar el modo crítico mediante Windows PowerShell

También puede especificar si se deben permitir sesiones de comunicación en caso de error que impida el archivado mediante el cmdlet **Set-CsArchivingConfiguration** con el parámetro BlockOnArchiveFailure.
  
Por ejemplo, el siguiente comando deshabilita las comunicaciones en caso de error de archivado:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

El siguiente comando habilita las comunicaciones en caso de error de archivado:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
