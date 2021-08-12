---
title: Administrar opciones de archivado en Skype Empresarial Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumen: obtenga información sobre cómo configurar las opciones de archivado para Skype Empresarial Server.'
ms.openlocfilehash: b2ed0644e64df1606141b94157920d98599fb020db7bdf39d522699fb88555ef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338154"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Administrar opciones de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo configurar las opciones de archivado para Skype Empresarial Server.
  
Inicialmente, configure el archivado en la implementación, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Las opciones de archivado determinan si: 
  
- Habilitar o deshabilitar el archivado
    
- Archivar sesiones de mensajería instantánea
    
- Archivar sesiones de conferencia web
    
- Bloquear actividad cuando el archivado no está disponible
    
- Usar Exchange integración
    
- Configurar la depuración y exportación de datos
    
Puede especificar opciones de configuración en los siguientes niveles:
  
- Configuración de nivel global que se crea de forma predeterminada al implementar Skype Empresarial Server
    
- Configuraciones de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico
    
- Configuraciones opcionales de nivel de grupo que especifican cómo se implementa el archivado para un grupo específico
    
Puede eliminar una configuración de sitio o una configuración de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados. Para obtener más información sobre cómo se implementan las configuraciones de archivado y la jerarquía de las configuraciones de archivado, vea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado mediante el Panel de control

Puede configurar las opciones de archivado mediante el Panel de control de la siguiente manera:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic **en Configuración de archivado.**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configure las opciones de archivado mediante Windows PowerShell

También puede configurar las opciones de archivado mediante los cmdlets Windows PowerShell que se enumeran en la tabla siguiente. Para obtener información detallada acerca de la sintaxis, incluidos todos los parámetros disponibles, [vea Skype Empresarial Server Shell de administración](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Devuelve información sobre las opciones de configuración de archivado de la organización.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crea un nuevo conjunto de opciones de configuración de mensajería instantánea (MI), que se pueden usar para habilitar o deshabilitar el guardado automático de sesiones de mensajería instantánea y para bloquear los mensajes instantáneos que no se puedan archivar.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Quita la colección especificada de opciones de archivado que se usan para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea (MI) y, opcionalmente, bloquear cualquier mensaje instantáneo que no se pueda archivar.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica una colección existente de opciones de configuración de archivado de mensajería instantánea (MI).  <br/> |
