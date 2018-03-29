---
title: Administrar el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumen: Conozca cómo administrar el archiving para Skype para Business Server 2015.'
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a>Administrar el archivado en Skype Empresarial Server 2015

**Resumen:** Aprenda a administrar el archivado de Skype para Business Server 2015.
  
Al implementar el archivado para su organización, se especifica la configuración inicial durante la implementación. Pero, posiblemente, en ocasiones desee cambiar la forma en que se implementa la compatibilidad del archivado para la administración diaria o para satisfacer los nuevos requisitos de su organización. Por ejemplo, es posible que necesite configurar la compatibilidad del archivado de manera diferente para un sitio, un grupo o usuarios específicos dentro de la organización. Para los usuarios alojados en Skype para Business Server, para ello, crear y personalizar las directivas de usuario y opciones de configuración de archivado. 
  
Antes de leer este tema, asegúrese de que está familiarizado con la información de [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) e [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado se habilita para los usuarios que están hospedados en Exchange y que tienen sus buzones definidos en la conservación local. Para obtener más información, vea [planear para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) y [Configurar la integración con almacenamiento de información de Exchange para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opciones de configuración del archivado

Las opciones de configuración del archivado especifican si:
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea (MI)
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la purga y la exportación de datos
    
Estas opciones se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, consulte [Administrar opciones de archivado en Skype para Business Server 2015](options.md).
  
## <a name="archiving-policies"></a>Directivas de archivado

Políticas de archiving de determinan si se debe archivar la siguiente:
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Estas directivas se pueden configurar de forma global, en el sitio o en el grupo. Para obtener más información, vea [administrar políticas de archiving en Skype para Business Server 2015](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Administrar el archivado con el Panel de control o con Windows PowerShell

Puede administrar el archivado con el Panel de control o con Windows PowerShell. En la siguiente tabla se resumen los cmdlets disponibles para ayudarlo a administrar el archivado. Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md). 


|**Cmdlet**|**Descripción**|
|:-----|:-----|
|CsArchivingData de exportación  <br/> |Exporta registros que se han almacenado en el Skype para base de datos de archivado de Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado en la organización.  <br/> |
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de la organización para las comunicaciones internas y externas.  <br/> |
|Concesión CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|CsArchivingDatabasePurge de invocación  <br/> |Purga manualmente los registros de la base de datos de archivado.  <br/> |
|Nueva CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Nueva CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Quitar CsArchivingConfiguration  <br/> |Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Quitar CsArchivingPolicy  <br/> |Quita el especificado mensajería instantánea (IM) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones IM que tienen lugar entre los usuarios internos, o bien todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados para el archivado.  <br/> |
|Conjunto de CsArchivingConfiguration  <br/> |Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
|Conjunto de CsArchivingPolicy  <br/> |Modifica una existente mensajería instantánea (IM política de archivado). Una directiva de archivado le da la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre los usuarios internos; También puede archivar las sesiones que tienen lugar entre los usuarios internos y los socios federados.  <br/> |
|Conjunto de CsArchivingServer  <br/> |Permite especificar una nueva ubicación de la base de datos para uno o más servidores de archivado.  <br/> |
   

