---
title: Administrar el archivado en Skype Empresarial Server
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumen: obtenga información sobre cómo administrar el archivado para Skype Empresarial Server.'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817740"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Administrar el archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar el archivado para Skype Empresarial Server.
  
Al implementar el archivado para su organización, especifique la configuración inicial durante la implementación. Sin embargo, puede haber ocasiones en las que desee cambiar la forma en que implementa la compatibilidad con el archivado para la administración diaria o para cumplir los nuevos requisitos de su organización. Por ejemplo, puede que necesite configurar la compatibilidad de archivado de forma diferente para un sitio específico, un grupo específico o usuarios específicos de la organización. Para los usuarios que están en Skype Empresarial Server, puede hacerlo creando y personalizando las opciones de configuración de archivado y las directivas de usuario. 
  
Antes de leer este tema, asegúrese de estar familiarizado con la información de [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Deploy archiving for Skype for Business [Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están en Exchange y tienen sus buzones en retención In-Place local. Para obtener más información, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opciones de configuración de archivado

Las opciones de configuración de archivado especifican si:
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la depuración y exportación de datos
    
Estas opciones se pueden establecer en el nivel global, de sitio o de grupo. Para obtener más información, vea [Administrar las opciones de archivado en Skype Empresarial Server.](options.md)
  
## <a name="archiving-policies"></a>Directivas de archivado

Las directivas de archivado determinan si se archiva lo siguiente:
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Estas directivas se pueden establecer en el nivel global, de sitio o de usuario. Para obtener más información, vea [Administrar directivas de archivado en Skype Empresarial Server.](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Administrar el archivado mediante el Panel de control o mediante Windows PowerShell

Puede administrar el archivado mediante el Panel de control o mediante Windows PowerShell. En la tabla siguiente se resumen los cmdlets disponibles para ayudarle a administrar el archivado. Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración [de Skype Empresarial Server.](../management-shell.md) 


|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta los registros almacenados en la base de datos de archivado de Skype Empresarial Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado de la organización.  <br/> |
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de la organización para las comunicaciones internas y externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de MI entre usuarios internos o archivar todas las sesiones de MI entre usuarios internos y socios externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purga manualmente los registros de la base de datos de archivado.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI), que se pueden usar para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea y para bloquear los mensajes instantáneos que no se pueden archivar.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea. Estas directivas permiten archivar todas las sesiones de mensajería instantánea entre usuarios internos o con usuarios externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la colección especificada de opciones de archivado que se usan para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea (MI) y, opcionalmente, para bloquear cualquier mensaje instantáneo que no se pueda archivar.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la directiva de archivado de mensajería instantánea (MI) especificada que determina si Skype Empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una colección existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (MI) existente. Una directiva de archivado le ofrece la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre usuarios internos; también puede archivar sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar una nueva ubicación de base de datos para uno o varios servidores de archivado.  <br/> |
   

