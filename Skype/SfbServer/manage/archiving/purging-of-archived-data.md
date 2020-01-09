---
title: Administrar la purga de datos archivados en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumen: Aprenda a administrar la purga de datos archivados en Skype empresarial Server.'
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991615"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Administrar la purga de datos archivados en Skype empresarial Server

**Resumen:** Aprenda a administrar la purga de datos archivados para Skype empresarial Server.
  
La base de datos de archivado no está pensada para la retención a largo plazo, y Skype empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que es necesario mover los datos a otro almacenamiento. Skype empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados en transcripciones que se pueden buscar. Es preciso que defina cuándo purgar los datos archivados y exportados. 
  
Para obtener más información sobre cómo exportar datos mediante el cmdlet **Export-CsArchivingData** , consulte [exportar datos archivados en Skype empresarial Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Administrar la purga de datos con el Panel de control

Para administrar la purga de datos archivados con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:
    
   - Para habilitar la purga, active la casilla **Habilitar purgado de los datos de archivado** y siga uno de estos procedimientos:
    
     - Para purgar todos los registros, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y, luego, especifique la cantidad de días.
    
     - Para purgar solo los datos que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
   - Para deshabilitar la purga, desactive la casilla **Habilitar purgado de los datos de archivado**.
    
5. Haga clic en **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Administrar la purga de datos con Windows PowerShell

Puede administrar la purga de datos archivados con los siguientes cmdlets de Windows PowerShell:
  
- El cmdlet **Set-CsArchivingConfiguration** junto con el parámetro EnablePurging permiten habilitar o deshabilitar la purga de los datos archivados.
    
- **Invoke-CsArchivingDatabasePurge** permite purgar los registros de forma manual desde la base de datos de archivado.
    
Por ejemplo, el siguiente comando permite la purga de todos los datos archivados. Después de ejecutar este comando, Skype empresarial Server purgará todos los registros de archivado anteriores al valor especificado para el parámetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

El siguiente comando limita la purga de los registros archivados que se han exportado a un archivo de datos (con el cmdlet **Export-CSArchivingData**). Es preciso que también establezca el parámetro PurgeExportedArchivesOnly en True ($True).
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Después de ejecutar este comando, Skype empresarial Server solo purgará los registros de archivado que cumplan con dos criterios: 1) son anteriores al valor especificado para el parámetro KeepArchivingDataForDays. y 2) se han exportado con el cmdlet **Export-CsArchivingData** .
  
Para deshabilitar la purga automatizada de los registros de archivado, establezca el parámetro EnablePurging en False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

En el ejemplo siguiente se usa el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros con más de 24 horas de antigüedad de la base de datos de archivado en ATL-SQL-001.contoso.com. Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False).
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
