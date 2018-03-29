---
title: Crear una configuración de archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumen: Conozca cómo crear una configuración de archiving para Skype para Business Server 2015.'
ms.openlocfilehash: 5675117d14d35e0055c7e494ce9476d421dda443
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server-2015"></a>Crear una configuración de archivado en Skype Empresarial Server 2015

**Resumen:** Aprenda a crear una configuración de archiving para Skype para Business Server 2015.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado con el Panel de control

Para configurar las opciones de archivado para un sitio o servidor determinado: 
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y haga una de las siguientes acciones: 
    
   - Para crear una configuración de archivado de sitio, haga clic en **Configuración de sitio** y, en **Seleccionar un sitio**, seleccione el sitio que se va a configurar para el archivado.
    
   - Para crear una configuración de archivado de grupo de servidores, haga clic en **Configuración del grupo de servidores** y, en **Seleccionar un grupo de servidores**, seleccione el grupo de servidores que se va a configurar para el archivado.
    
5. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea (MI) y conferencias web**.
    
   - Para deshabilitar el archivado para esta configuración, haga clic en **Deshabilitar archivado**.
    
6. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para utilizar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
     - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
     - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar las opciones de archivado con Windows PowerShell

También puede configurar las opciones de archivado de un sitio o un grupo determinado con el cmdlet **New-CsArchivingConfiguration**.
  
El comando siguiente crea una colección de opciones de configuración de archivado para el sitio de Redmond:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Como no se especificó ningún parámetro (aparte del parámetro obligatorio Identity) en el comando anterior, la colección nueva de opciones de configuración usará los valores predeterminados para todas sus propiedades. 
  
Para crear una configuración que use valores de propiedad distintos, incluya el valor del parámetro y el parámetro adecuados. En el siguiente ejemplo, se crea una colección de opciones de configuración que, de forma predeterminada, permite el archivado solo de sesiones de mensajería instantánea:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea si el servicio de archivado no está disponible:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .