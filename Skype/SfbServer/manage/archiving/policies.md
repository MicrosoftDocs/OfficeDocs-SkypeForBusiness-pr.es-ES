---
title: Administrar directivas de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: obtenga información sobre cómo administrar directivas de usuario para el archivado de Skype Empresarial Server.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828556"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Administrar directivas de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar directivas de usuario para el archivado de Skype Empresarial Server.
  
Las directivas de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Las directivas de archivado determinan si se va a archivar: 
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Las directivas de archivado se pueden establecer en el nivel global, de sitio o de usuario.
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están en Exchange y tienen sus buzones en retención In-Place local. Para obtener más información, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Administrar directivas de archivado mediante el Panel de control

Puede administrar las directivas de archivado mediante el Panel de control de la siguiente manera:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Directiva de archivado**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Administrar directivas de archivado mediante Windows PowerShell

También puede configurar directivas de archivado con los cmdlets Windows PowerShell que se enumeran en la tabla siguiente. Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración [de Skype Empresarial Server.](../management-shell.md)
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de sesiones de mensajería instantánea (MI) de su organización.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de MI entre usuarios internos o archivar todas las sesiones de MI entre usuarios internos y socios externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea. Estas directivas permiten archivar todas las sesiones de mensajería instantánea entre usuarios internos o con usuarios externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la directiva de archivado de mensajería instantánea (MI) especificada que determina si Skype Empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (MI) existente. Una directiva de archivado le ofrece la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre usuarios internos; también puede archivar sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
   

