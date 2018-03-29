---
title: Administrar la purga de datos archivados en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumen: Conozca cómo administrar el proceso de purga de los datos archivados de Skype para Business Server 2015.'
ms.openlocfilehash: caeddcd927c20f0622cbd45b6d93abb2bf5d6618
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server-2015"></a>Administrar la purga de datos archivados en Skype Empresarial Server 2015

**Resumen:** Aprenda a administrar el proceso de purga de los datos archivados de Skype para Business Server 2015.
  
La base de datos de archivado no está pensado para la retención a largo plazo y Skype para el año 2015 de Business Server no proporciona una solución de e-discovery (Buscar) para los datos archivados, por lo que deben moverse a otro almacenamiento datos. Skype para Business Server proporciona una herramienta de exportación de sesión que puede utilizar para exportar los datos archivados en los expedientes que se puede buscar. Es preciso que defina cuándo purgar los datos archivados y exportados. 
  
Para obtener más información sobre cómo exportar datos mediante el cmdlet **Export-CsArchivingData** , vea [Exportar datos archivados en Skype para Business Server 2015](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Administrar la purga de datos con el Panel de control

Para administrar la purga de datos archivados con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
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
    
Por ejemplo, el siguiente comando permite la purga de todos los datos archivados. Después de ejecuta este comando, Skype para Business Server purgará archivados y todos los registros más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

El siguiente comando limita la purga de los registros archivados que se han exportado a un archivo de datos (con el cmdlet **Export-CSArchivingData**). Es preciso que también establezca el parámetro PurgeExportedArchivesOnly en True ($True).
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Después de ejecuta este comando, Skype para Business Server sólo purgará el archivado de los registros que cumplan dos criterios: 1) son más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays; y, 2) se han exportado mediante el cmdlet **Export-CsArchivingData** .
  
Para deshabilitar la purga automatizada de los registros de archivado, establezca el parámetro EnablePurging en False ($False):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

En el ejemplo siguiente se utiliza el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros antiguos de más de 24 horas desde la base de datos de archivado en atl-sql-001.contoso.com. Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False):
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```