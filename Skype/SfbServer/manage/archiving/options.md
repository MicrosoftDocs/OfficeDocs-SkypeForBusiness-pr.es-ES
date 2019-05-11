---
title: Administrar las opciones de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumen: Obtenga información sobre cómo configurar las opciones de archivado para Skype para Business Server.'
ms.openlocfilehash: 77e9d8469d3c99ee0f45e97a002d371481d81299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885020"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Administrar las opciones de archivado en Skype para Business Server

**Resumen:** Obtenga información sobre cómo configurar las opciones de archivado para Skype para Business Server.
  
Configura inicialmente el archivado en la implementación, pero puede cambiar, agregar o eliminar la configuración tras la implementación. Las opciones de archivado determinan si: 
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea (MI)
    
- Archivar sesiones de conferencia web
    
- Bloquear la actividad cuando el archivado no está disponible
    
- Usar la integración de Exchange
    
- Configurar la purga y la exportación de datos
    
Puede especificar las opciones de configuración en los siguientes niveles:
  
- Configuración de nivel global que se crea de forma predeterminada al implementar Skype para Business Server
    
- En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico
    
- Configuraciones opcionales de nivel de grupo de servidores que especifican cómo se implementa el archivado para un grupo de servidores específico
    
Es posible eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados. Para obtener información detallada acerca de cómo se implementan las configuraciones de archivado y la jerarquía de directivas, consulte [Plan para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado con el Panel de control

Puede configurar las opciones de archivado con el Panel de control de esta manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración de archivado**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar las opciones de archivado con Windows PowerShell

También puede configurar las opciones de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente. Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado en la organización.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
