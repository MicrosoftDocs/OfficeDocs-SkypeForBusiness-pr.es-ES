---
title: Administración de directivas de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Obtenga información sobre cómo administrar las directivas de usuario para el archivado de Skype para Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873243"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Administración de directivas de archivado en Skype para Business Server

**Resumen:** Obtenga información sobre cómo administrar las directivas de usuario para el archivado de Skype para Business Server.
  
Inicialmente, configurar directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar las configuraciones de después de la implementación. Las directivas de archivado determinan si desea archivar: 
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Directivas de archivado pueden ser conjunto a nivel global, de sitio o de nivel de usuario.
  
> [!NOTE]
> Si se habilita la integración de Microsoft Exchange para la implementación, el control de las directivas de Exchange si el archivado está habilitado para los usuarios que están ubicados en Exchange y disponer sus buzones en suspensión en contexto. Para obtener información detallada, vea [Planear el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) y [Configure la integración con el almacenamiento de Exchange de Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Administrar directivas de archivado con el Panel de control

Puede administrar las directivas de archivado con el Panel de control de esta manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Directiva de archivado**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Administrar las directivas de archivado con Windows PowerShell

También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente. Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita el especificado mensajería instantánea (mi) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre los usuarios internos, o todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados de archivado.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una existente mensajería instantánea (mi) Directiva de archivado. Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones de mensajería instantánea y las conferencias que tienen lugar entre los usuarios internos; También puede archivar sesiones que tienen lugar entre los usuarios internos y los socios federados.  <br/> |
   

