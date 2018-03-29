---
title: Administrar las opciones de archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumen: Conozca cómo configurar opciones de archivado de Skype para Business Server 2015.'
ms.openlocfilehash: 29800fef7054cd0e82f203d2ad6ec1ed53251ca4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-options-in-skype-for-business-server-2015"></a>Administrar las opciones de archivado en Skype Empresarial Server 2015

**Resumen:** Aprenda a configurar las opciones de archivado de Skype para Business Server 2015.
  
Configura inicialmente el archivado en la implementación, pero puede cambiar, agregar o eliminar la configuración tras la implementación. Las opciones de archivado determinan si: 
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea (MI)
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la purga y la exportación de datos
    
Puede especificar las opciones de configuración en los siguientes niveles:
  
- Configuración de nivel global por defecto se crea al implementar Skype para Business Server
    
- En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico
    
- Configuraciones de nivel de grupo opcionales que especifican cómo se implementa el archivado para un grupo específico
    
Es posible eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados. Para obtener más información acerca de cómo se implementan las configuraciones de archivado y la jerarquía del archiving de configuraciones, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado con el Panel de control

Puede configurar las opciones de archivado con el Panel de control de esta manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración de archivado**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar las opciones de archivado con Windows PowerShell

También puede configurar las opciones de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente. Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado en la organización.  <br/> |
|Nueva CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Quitar CsArchivingConfiguration  <br/> |Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Conjunto de CsArchivingConfiguration  <br/> |Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |