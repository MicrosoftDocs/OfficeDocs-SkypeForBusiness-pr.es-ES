---
title: Administrar el archivado en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumen: Obtenga información sobre cómo administrar el archivado de Skype para Business Server.'
ms.openlocfilehash: 28d69bbdb46a2046f5d6b1898dced73d5e286a6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920650"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Administrar el archivado en Skype para Business Server

**Resumen:** Obtenga información sobre cómo administrar el archivado de Skype para Business Server.
  
Al implementar el archivado para su organización, se especifica la configuración inicial durante la implementación. Pero, posiblemente, en ocasiones desee cambiar la forma en que se implementa la compatibilidad del archivado para la administración diaria o para satisfacer los nuevos requisitos de su organización. Por ejemplo, es posible que necesite configurar la compatibilidad del archivado de manera diferente para un sitio, un grupo o usuarios específicos dentro de la organización. Para los usuarios alojados en Skype para Business Server, para ello, creación y personalización de opciones de configuración de archivado y las directivas de usuario. 
  
Antes de leer este tema, debe asegurarse de que está familiarizado con la información de [planeación para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) y [Deploy archivado para Skype para Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado se habilita para los usuarios que están hospedados en Exchange y que tienen sus buzones definidos en la conservación local. Para obtener información detallada, vea [Planear el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) y [Configure la integración con el almacenamiento de Exchange de Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opciones de configuración del archivado

Las opciones de configuración del archivado especifican si:
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea (MI)
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la purga y la exportación de datos
    
Estas opciones se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, vea [administrar las opciones de archivado en Skype para Business Server](options.md).
  
## <a name="archiving-policies"></a>Directivas de archivado

Las directivas de archivado determinan si desea archivar lo siguiente:
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Estas directivas se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, vea [administrar las directivas de archivado en Skype para Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Administrar el archivado con el Panel de control o con Windows PowerShell

Puede administrar el archivado con el Panel de control o con Windows PowerShell. En la siguiente tabla se resumen los cmdlets disponibles para ayudarlo a administrar el archivado. Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md). 


|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta los registros que se han almacenado en el Skype para la base de datos de archivado de servidor empresarial.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado en la organización.  <br/> |
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de la organización para las comunicaciones internas y externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purga manualmente los registros de la base de datos de archivado.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|New-CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Quita el especificado mensajería instantánea (mi) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre los usuarios internos, o todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados de archivado.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica una existente mensajería instantánea (mi) Directiva de archivado. Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones de mensajería instantánea y las conferencias que tienen lugar entre los usuarios internos; También puede archivar sesiones que tienen lugar entre los usuarios internos y los socios federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar una nueva ubicación de la base de datos para uno o más servidores de archivado.  <br/> |
   

