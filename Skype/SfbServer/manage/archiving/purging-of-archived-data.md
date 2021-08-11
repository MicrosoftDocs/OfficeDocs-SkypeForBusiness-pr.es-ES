---
title: Administrar la depuración de datos archivados en Skype Empresarial Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Summary: Learn how to manage purging of archived data for Skype Empresarial Server.'
ms.openlocfilehash: f6eafbacedc715dc3684a16eb17cd5e1b1ae59923046af5cf180e92bbf6a2266
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307081"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Administrar la depuración de datos archivados en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar la depuración de datos archivados para Skype Empresarial Server.
  
La base de datos de archivado no está diseñada para la retención a largo plazo y Skype Empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que los datos deben moverse a otro almacenamiento. Skype Empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados a transcripciones que se pueden buscar. Debe definir cuándo se deben purgar los datos archivados y exportados. 
  
Para obtener más información acerca de la exportación de datos mediante el cmdlet **Export-CsArchivingData,** vea [Export archived data in Skype Empresarial Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Administrar la depuración de datos mediante el Panel de control

Para administrar la depuración de datos archivados mediante el Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
   - Para habilitar la depuración, active la casilla Habilitar **depuración** de datos de archivado y, a continuación, realice una de las siguientes acciones:
    
     - Para purgar todos los registros, haga clic en purgar los datos de archivado exportados y los datos de archivado almacenados después de la duración máxima **(días)** y, a continuación, especifique el número de días.
    
     - Para purgar solo los datos exportados, haga clic **en Purgar solo datos de archivado exportados.**
    
   - Para deshabilitar la depuración, desactive la casilla Habilitar **depuración** de datos de archivado.
    
5. Haga clic en **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Administrar la depuración de datos mediante Windows PowerShell

Puede administrar la depuración de datos archivados mediante los siguientes cmdlets Windows PowerShell datos:
  
- El cmdlet **Set-CsArchivingConfiguration** con el parámetro EnablePurging le permite habilitar o deshabilitar la depuración de datos archivados.
    
- **Invoke-CsArchivingDatabasePurge** le permite purgar manualmente los registros de la base de datos de archivado.
    
Por ejemplo, el siguiente comando habilita la depuración de todos los datos archivados. Después de ejecutar este comando, Skype Empresarial Server purgará todos los registros de archivado anteriores al valor especificado para el parámetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

El siguiente comando limita la depuración a los registros archivados que se han exportado a un archivo de datos (mediante el cmdlet **Export-CSArchivingData).** También debe establecer el parámetro PurgeExportedArchivesOnly en True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Después de ejecutar este comando, Skype Empresarial Server purgará solo los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays; y, 2) se han exportado mediante el cmdlet **Export-CsArchivingData.**
  
Para deshabilitar la depuración automatizada de registros de archivado, establezca el parámetro EnablePurging en False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

En el ejemplo siguiente se usa el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros con más de 24 horas de antigüedad de la base de datos de archivado en atl-sql-001.contoso.com. Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
