---
title: Administrar las directivas de archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Conozca cómo administrar directivas de usuario para archiving de Skype para Business Server 2015.'
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a>Administrar las directivas de archivado en Skype Empresarial Server 2015

**Resumen:** Obtenga información sobre cómo administrar las directivas de usuario para archiving de Skype para Business Server 2015.
  
Inicialmente configurar políticas de archiving al implementar archiving, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Políticas de archiving de determinan si se debe archivar: 
  
- Comunicaciones internas
    
- Comunicaciones externas
    
Políticas de archiving pueden ser a nivel de usuario, sitio o conjunto a nivel global.
  
> [!NOTE]
> Si habilita la integración de Microsoft Exchange para la implementación, el control de directivas de Exchange si el archivado está habilitado para los usuarios que están alojados en Exchange y han puesto a sus buzones en mantenga In situ. Para obtener más información, vea [planear para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) y [Configurar la integración con almacenamiento de información de Exchange para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Administrar directivas de archivado con el Panel de control

Puede administrar las directivas de archivado con el Panel de control de esta manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Directiva de archivado**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Administrar las directivas de archivado con Windows PowerShell

También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente. Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.  <br/> |
|Concesión CsArchivingPolicy  <br/> |Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios. Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Nueva CsArchivingPolicy  <br/> |Crea directivas de archivado de sesiones de mensajería instantánea (MI). Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.  <br/> |
|Quitar CsArchivingPolicy  <br/> |Quita el especificado mensajería instantánea (IM) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones IM que tienen lugar entre los usuarios internos, o bien todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados para el archivado.  <br/> |
|Conjunto de CsArchivingPolicy  <br/> |Modifica una existente mensajería instantánea (IM política de archivado). Una directiva de archivado le da la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre los usuarios internos; También puede archivar las sesiones que tienen lugar entre los usuarios internos y los socios federados.  <br/> |
   

