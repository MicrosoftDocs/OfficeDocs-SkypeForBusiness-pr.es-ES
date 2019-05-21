---
title: Administrar directivas de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Aprenda a administrar directivas de usuario para archivar en Skype empresarial Server.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278429"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Administrar directivas de archivado en Skype empresarial Server

**Resumen:** Aprenda a administrar directivas de usuario para archivar en Skype empresarial Server.
  
Inicialmente, debe configurar las directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Las directivas de archivado determinan si se debe archivar: 
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Las directivas de archivado se pueden establecer en el nivel global, de sitio o de usuario.
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange y si sus buzones se colocan en la retención local. Para obtener más información, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) y [configurar la integración con el almacenamiento de Exchange para Skype empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Administrar directivas de archivado con el Panel de control

Puede administrar las directivas de archivado con el Panel de control de esta manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Directiva de archivado**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Administrar las directivas de archivado con Windows PowerShell

También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente. Para más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte [Shell de administración de Skype empresarial Server](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la Directiva de archivado de mensajería instantánea (mi) especificada que determina si Skype empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que se realicen entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (mi) existente. Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones y conferencias de mensajería instantánea que se producen entre usuarios internos; también puede archivar las sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
   

