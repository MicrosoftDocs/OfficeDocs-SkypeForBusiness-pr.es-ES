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
ms.openlocfilehash: a3d23eefe673f74162e2c23a3d0476c1251ecad7e4719ccc1a7c6347f564deed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320302"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Administrar el archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar el archivado para Skype Empresarial Server.
  
Al implementar el archivado de la organización, se especifica la configuración inicial durante la implementación. Sin embargo, puede haber ocasiones en las que desee cambiar la forma en que implementa la compatibilidad de archivado para la administración diaria o para cumplir con los nuevos requisitos de su organización. Por ejemplo, es posible que deba configurar la compatibilidad de archivado de forma diferente para un sitio específico, un grupo de servidores específico o usuarios específicos de la organización. Para los usuarios que se Skype Empresarial Server, puede hacerlo creando y personalizando las opciones de configuración de archivado y las directivas de usuario. 
  
Antes de leer este tema, asegúrese de estar familiarizado con la información de [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md) and Deploy archiving for [Skype Empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están ubicados en Exchange y tienen sus buzones en espera In-Place. Para obtener más información, vea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for [Skype Empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opciones de configuración de archivado

Las opciones de configuración de archivado especifican si:
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea
    
- Archivar sesiones de conferencia web
    
- Bloquear actividad cuando el archivado no está disponible
    
- Usar Exchange integración
    
- Configurar la depuración y exportación de datos
    
Estas opciones se pueden establecer en el nivel global, de sitio o de grupo. Para obtener más información, vea [Manage archiving options in Skype Empresarial Server](options.md).
  
## <a name="archiving-policies"></a>Directivas de archivado

Las directivas de archivado determinan si se archivará lo siguiente:
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Estas directivas se pueden establecer en el nivel global, de sitio o de usuario. Para obtener más información, vea [Manage archiving policies in Skype Empresarial Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Administrar el archivado mediante el Panel de control o mediante Windows PowerShell

Puede administrar el archivado mediante el Panel de control o mediante Windows PowerShell. En la tabla siguiente se resumen los cmdlets disponibles para ayudarle a administrar el archivado. Para obtener información detallada acerca de la sintaxis, incluidos todos los parámetros disponibles, [vea Skype Empresarial Server Shell de administración](../management-shell.md). 


|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta registros almacenados en la base de datos Skype Empresarial Server de archivado.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado de la organización.  <br/> |
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de la organización para comunicaciones internas y externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesión de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de MI entre usuarios internos o archivar todas las sesiones de MI entre usuarios internos y socios externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purga manualmente los registros de la base de datos de archivado.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de opciones de configuración de mensajería instantánea (MI), que se pueden usar para habilitar o deshabilitar el guardado automático de sesiones de mensajería instantánea y para bloquear los mensajes instantáneos que no se puedan archivar.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea. Estas directivas permiten archivar todas las sesiones de mensajería instantánea entre usuarios internos o con usuarios externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la colección especificada de opciones de archivado que se usan para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea (MI) y, opcionalmente, bloquear cualquier mensaje instantáneo que no se pueda archivar.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la directiva de archivado de mensajería instantánea (MI) especificada que determina si Skype Empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que se llevan a cabo entre usuarios internos y/o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una colección existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (MI) existente. Una directiva de archivado le ofrece la capacidad de archivar todas las sesiones y conferencias de mensajería instantánea que tienen lugar entre usuarios internos; también puede archivar sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar una nueva ubicación de base de datos para uno o varios servidores de archivado.  <br/> |
   

