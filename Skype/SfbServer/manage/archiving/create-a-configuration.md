---
title: Crear una configuración de archivado en Skype Empresarial Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumen: obtenga información sobre cómo crear una configuración de archivado para Skype Empresarial Server.'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817660"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Crear una configuración de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo crear una configuración de archivado para Skype Empresarial Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado mediante el Panel de control

Para configurar las opciones de archivado para un sitio o grupo específico: 
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y elija una de las siguientes acciones: 
    
   - Para crear una configuración de archivado de sitio, haga clic en Configuración del sitio y, **a** continuación, en Seleccionar un sitio, seleccione el sitio que desea configurar para el archivado.
    
   - Para crear una configuración de archivado de grupo, haga clic en Configuración del grupo de servidores y, **a** continuación, en Seleccionar un grupo, seleccione el grupo que desea configurar para el archivado.
    
5. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.
    
   - Para habilitar el archivado tanto para las sesiones de mensajería instantánea como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - Para deshabilitar el archivado para esta configuración, haga clic **en Deshabilitar archivado.**
    
6. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
   - Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de integración de **Microsoft Exchange.**
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
    
     - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
    
     - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configure las opciones de archivado mediante Windows PowerShell

También puede configurar las opciones de archivado para un sitio o grupo específico mediante el cmdlet **New-CsArchivingConfiguration.**
  
El comando siguiente crea una colección de valores de configuración de archivado para el sitio de Redmond:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. 
  
Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. En el siguiente ejemplo se crea una colección de opciones de configuración de archivado que, de forma predeterminada, solo permiten el archivado de sesiones de mensajería instantánea:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Si lo desea, puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea del servicio de archivado no está disponible:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)
