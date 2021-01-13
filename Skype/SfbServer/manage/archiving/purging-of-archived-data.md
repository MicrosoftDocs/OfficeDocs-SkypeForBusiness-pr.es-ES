---
title: Administrar la purga de datos archivados en Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre cómo administrar la purga de datos archivados para Skype Empresarial Server.'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828540"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Administrar la purga de datos archivados en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo administrar la purga de datos archivados para Skype Empresarial Server.
  
La base de datos de archivado no está pensada para la retención a largo plazo y Skype Empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que los datos deben moverse a otro almacenamiento. Skype Empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados a transcripciones que se pueden buscar. Debe definir cuándo se deben purgar los datos archivados y exportados. 
  
Para obtener más información acerca de la exportación de datos mediante el cmdlet **Export-CsArchivingData,** vea Exportar datos archivados [en Skype Empresarial Server.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Administrar la purga de datos mediante el Panel de control

Para administrar la purga de datos archivados mediante el Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
   - Para habilitar la depuración, active la casilla Habilitar purgado de datos de archivado y, a continuación, realice una de las siguientes acciones: 
    
     - Para purgar todos los registros, haga clic en Purgar datos de archivado exportados y datos de archivado almacenados después de la duración máxima **(días)** y, a continuación, especifique el número de días.
    
     - Para purgar solo los datos exportados, haga clic en **Purgar solo los datos de archivado exportados.**
    
   - Para deshabilitar la purga, desactive la casilla Habilitar **purgado de datos de** archivado.
    
5. Haga clic en **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Administrar la purga de datos mediante Windows PowerShell

Puede administrar la purga de datos archivados mediante los siguientes cmdlets Windows PowerShell datos:
  
- El cmdlet **Set-CsArchivingConfiguration** con el parámetro EnablePurging permite habilitar o deshabilitar la depuración de datos archivados.
    
- **Invoke-CsArchivingDatabasePurge** permite purgar manualmente los registros de la base de datos de archivado.
    
Por ejemplo, el siguiente comando permite purgar todos los datos archivados. Después de ejecutar este comando, Skype Empresarial Server purgará todos los registros de archivado anteriores al valor especificado para el parámetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

El siguiente comando limita la depuración de registros archivados que se han exportado a un archivo de datos (mediante el cmdlet **Export-CSArchivingData).** También debe establecer el parámetro PurgeExportedArchivesOnly en True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Después de ejecutar este comando, Skype Empresarial Server solo purgará los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays; y, 2) se han exportado mediante el cmdlet **Export-CsArchivingData.**
  
Para deshabilitar la purga automatizada de registros de archivado, establezca el parámetro EnablePurging en False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

En el siguiente ejemplo se usa el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros de más de 24 horas de antigüedad de la base de datos de archivado en atl-sql-001.contoso.com. Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
