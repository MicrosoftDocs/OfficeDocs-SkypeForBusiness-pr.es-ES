---
title: Crear una configuración de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumen: Aprenda a crear una configuración de archivado para Skype empresarial Server.'
ms.openlocfilehash: 58d817cea4c1caceff37bd132cd4f5a61445cdb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286221"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Crear una configuración de archivado en Skype empresarial Server

**Resumen:** Aprenda a crear una configuración de archivado para Skype empresarial Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar las opciones de archivado con el Panel de control

Para configurar las opciones de archivado para un sitio o servidor determinado: 
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
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
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
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

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .
