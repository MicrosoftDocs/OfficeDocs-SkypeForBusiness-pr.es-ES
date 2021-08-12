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
description: 'Summary: Learn how to manage user policies for archiving for Skype Empresarial Server.'
ms.openlocfilehash: d04406de44510c1d1bc63921e5fa6c5dab817ad81c8cba7dc391ec0ee8454716
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329594"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Administrar directivas de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar directivas de usuario para el archivado de Skype Empresarial Server.
  
Inicialmente, configura directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Las directivas de archivado determinan si se archivarán: 
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Las directivas de archivado se pueden establecer en el nivel global, de sitio o de usuario.
  
> [!NOTE]
> Si ha habilitado la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que se encuentran en Exchange y tienen sus buzones en espera In-Place. Para obtener más información, vea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for [Skype Empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Administrar directivas de archivado mediante el Panel de control

Puede administrar las directivas de archivado mediante el Panel de control de la siguiente manera:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Directiva de archivado**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Administrar directivas de archivado mediante Windows PowerShell

También puede configurar directivas de archivado mediante los cmdlets Windows PowerShell que se enumeran en la tabla siguiente. Para obtener información detallada acerca de la sintaxis, incluidos todos los parámetros disponibles, [vea Skype Empresarial Server Shell de administración](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de sesiones de mensajería instantánea (MI) de su organización.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesión de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de MI entre usuarios internos o archivar todas las sesiones de MI entre usuarios internos y socios externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea. Estas directivas permiten archivar todas las sesiones de mensajería instantánea entre usuarios internos o con usuarios externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la directiva de archivado de mensajería instantánea (MI) especificada que determina si Skype Empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que se llevan a cabo entre usuarios internos y/o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (MI) existente. Una directiva de archivado le ofrece la capacidad de archivar todas las sesiones y conferencias de mensajería instantánea que tienen lugar entre usuarios internos; también puede archivar sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
   

