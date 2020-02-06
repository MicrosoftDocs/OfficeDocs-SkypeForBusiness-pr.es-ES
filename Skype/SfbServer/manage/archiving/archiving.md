---
title: Administrar el archivado en Skype empresarial Server
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumen: Aprenda a administrar el archivado de Skype empresarial Server.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819002"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Administrar el archivado en Skype empresarial Server

**Resumen:** Aprenda a administrar el archivado de Skype empresarial Server.
  
Al implementar el archivado para su organización, se especifica la configuración inicial durante la implementación. Pero, posiblemente, en ocasiones desee cambiar la forma en que se implementa la compatibilidad del archivado para la administración diaria o para satisfacer los nuevos requisitos de su organización. Por ejemplo, es posible que necesite configurar la compatibilidad del archivado de manera diferente para un sitio, un grupo o usuarios específicos dentro de la organización. Para los usuarios alojados en Skype empresarial Server, debe crear y personalizar las opciones de configuración y las directivas de usuario. 
  
Antes de leer este tema, asegúrese de que está familiarizado con la información contenida en [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) e [implementar el archivado de Skype empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado se habilita para los usuarios que están hospedados en Exchange y que tienen sus buzones definidos en la conservación local. Para obtener más información, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) y [configurar la integración con el almacenamiento de Exchange para Skype empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opciones de configuración del archivado

Las opciones de configuración del archivado especifican si:
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea (MI)
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la purga y la exportación de datos
    
Estas opciones se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, vea [administrar las opciones de archivado en Skype empresarial Server](options.md).
  
## <a name="archiving-policies"></a>Directivas de archivado

Las directivas de archivado determinan si archivar lo siguiente:
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Estas directivas se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, vea [Administrar directivas de archivado en Skype empresarial Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Administrar el archivado con el Panel de control o con Windows PowerShell

Puede administrar el archivado con el Panel de control o con Windows PowerShell. En la siguiente tabla se resumen los cmdlets disponibles para ayudarlo a administrar el archivado. Para más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte [Shell de administración de Skype empresarial Server](../management-shell.md). 


|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta los registros que se han almacenado en la base de datos de archivado de Skype empresarial Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado en la organización.  <br/> |
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de la organización para las comunicaciones internas y externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purga manualmente los registros de la base de datos de archivado.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita la Directiva de archivado de mensajería instantánea (mi) especificada que determina si Skype empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que se realicen entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una directiva de archivado de mensajería instantánea (mi) existente. Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones y conferencias de mensajería instantánea que se producen entre usuarios internos; también puede archivar las sesiones que tienen lugar entre usuarios internos y socios federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar una nueva ubicación de la base de datos para uno o más servidores de archivado.  <br/> |
   

