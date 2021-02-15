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
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="47be3-103">Administrar la purga de datos archivados en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="47be3-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="47be3-104">**Resumen:** Obtenga información sobre cómo administrar la purga de datos archivados para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="47be3-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="47be3-105">La base de datos de archivado no está pensada para la retención a largo plazo y Skype Empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que los datos deben moverse a otro almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="47be3-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="47be3-106">Skype Empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados a transcripciones que se pueden buscar.</span><span class="sxs-lookup"><span data-stu-id="47be3-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="47be3-107">Debe definir cuándo se deben purgar los datos archivados y exportados.</span><span class="sxs-lookup"><span data-stu-id="47be3-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="47be3-108">Para obtener más información acerca de la exportación de datos mediante el cmdlet **Export-CsArchivingData,** vea Exportar datos archivados [en Skype Empresarial Server.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="47be3-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="47be3-109">Administrar la purga de datos mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="47be3-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="47be3-110">Para administrar la purga de datos archivados mediante el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="47be3-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="47be3-111">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="47be3-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="47be3-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="47be3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="47be3-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="47be3-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="47be3-114">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47be3-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="47be3-115">Para habilitar la depuración, active la casilla Habilitar purgado de datos de archivado y, a continuación, realice una de las siguientes acciones: </span><span class="sxs-lookup"><span data-stu-id="47be3-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="47be3-116">Para purgar todos los registros, haga clic en Purgar datos de archivado exportados y datos de archivado almacenados después de la duración máxima **(días)** y, a continuación, especifique el número de días.</span><span class="sxs-lookup"><span data-stu-id="47be3-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="47be3-117">Para purgar solo los datos exportados, haga clic en **Purgar solo los datos de archivado exportados.**</span><span class="sxs-lookup"><span data-stu-id="47be3-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="47be3-118">Para deshabilitar la purga, desactive la casilla Habilitar **purgado de datos de** archivado.</span><span class="sxs-lookup"><span data-stu-id="47be3-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="47be3-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="47be3-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="47be3-120">Administrar la purga de datos mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47be3-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="47be3-121">Puede administrar la purga de datos archivados mediante los siguientes cmdlets Windows PowerShell datos:</span><span class="sxs-lookup"><span data-stu-id="47be3-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="47be3-122">El cmdlet **Set-CsArchivingConfiguration** con el parámetro EnablePurging permite habilitar o deshabilitar la purga de datos archivados.</span><span class="sxs-lookup"><span data-stu-id="47be3-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="47be3-123">**Invoke-CsArchivingDatabasePurge** permite purgar manualmente los registros de la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="47be3-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="47be3-124">Por ejemplo, el siguiente comando permite purgar todos los datos archivados.</span><span class="sxs-lookup"><span data-stu-id="47be3-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="47be3-125">Después de ejecutar este comando, Skype Empresarial Server purgará todos los registros de archivado anteriores al valor especificado para el parámetro KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="47be3-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="47be3-126">El siguiente comando limita la depuración de registros archivados que se han exportado a un archivo de datos (mediante el cmdlet **Export-CSArchivingData).**</span><span class="sxs-lookup"><span data-stu-id="47be3-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="47be3-127">También debe establecer el parámetro PurgeExportedArchivesOnly en True ($True):</span><span class="sxs-lookup"><span data-stu-id="47be3-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="47be3-128">Después de ejecutar este comando, Skype Empresarial Server solo purgará los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays; y, 2) se han exportado mediante el cmdlet **Export-CsArchivingData.**</span><span class="sxs-lookup"><span data-stu-id="47be3-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="47be3-129">Para deshabilitar la purga automatizada de registros de archivado, establezca el parámetro EnablePurging en False ($False):</span><span class="sxs-lookup"><span data-stu-id="47be3-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="47be3-130">En el siguiente ejemplo se usa el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros de más de 24 horas de antigüedad de la base de datos de archivado en atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="47be3-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="47be3-131">Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False):</span><span class="sxs-lookup"><span data-stu-id="47be3-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
