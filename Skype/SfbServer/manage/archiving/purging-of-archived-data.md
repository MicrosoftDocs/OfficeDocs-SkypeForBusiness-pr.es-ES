---
title: Administrar la purga de datos archivados de Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumen: Obtenga información sobre cómo administrar el proceso de purga de los datos archivados de Skype para Business Server.'
ms.openlocfilehash: 5483871d69932239f5d6e654c95edf1feac7b9d9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884128"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="60b37-103">Administrar la purga de datos archivados de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="60b37-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="60b37-104">**Resumen:** Obtenga información sobre cómo administrar el proceso de purga de los datos archivados de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="60b37-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="60b37-105">La base de datos de archivado no está pensada para la retención a largo plazo y Skype para Business Server no proporciona una solución de exhibición de documentos electrónicos (búsqueda) para los datos archivados, por lo que necesitan datos va a mover a otro almacén.</span><span class="sxs-lookup"><span data-stu-id="60b37-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="60b37-106">Skype para Business Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados en transcripciones que admite búsquedas.</span><span class="sxs-lookup"><span data-stu-id="60b37-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="60b37-107">Es preciso que defina cuándo purgar los datos archivados y exportados.</span><span class="sxs-lookup"><span data-stu-id="60b37-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="60b37-108">Para obtener más información acerca de la exportación de datos mediante el cmdlet **Export-CsArchivingData** , vea [Exportar datos archivados en Skype para Business Server](export-archived-data.md).</span><span class="sxs-lookup"><span data-stu-id="60b37-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="60b37-109">Administrar la purga de datos con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="60b37-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="60b37-110">Para administrar la purga de datos archivados con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="60b37-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="60b37-111">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="60b37-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="60b37-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="60b37-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="60b37-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="60b37-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="60b37-114">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60b37-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="60b37-115">Para habilitar la purga, active la casilla **Habilitar purgado de los datos de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="60b37-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="60b37-116">Para purgar todos los registros, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y, luego, especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="60b37-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="60b37-117">Para purgar solo los datos que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="60b37-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="60b37-118">Para deshabilitar la purga, desactive la casilla **Habilitar purgado de los datos de archivado**.</span><span class="sxs-lookup"><span data-stu-id="60b37-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="60b37-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="60b37-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="60b37-120">Administrar la purga de datos con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60b37-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="60b37-121">Puede administrar la purga de datos archivados con los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60b37-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="60b37-122">El cmdlet **Set-CsArchivingConfiguration** junto con el parámetro EnablePurging permiten habilitar o deshabilitar la purga de los datos archivados.</span><span class="sxs-lookup"><span data-stu-id="60b37-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="60b37-123">**Invoke-CsArchivingDatabasePurge** permite purgar los registros de forma manual desde la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="60b37-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="60b37-124">Por ejemplo, el siguiente comando permite la purga de todos los datos archivados.</span><span class="sxs-lookup"><span data-stu-id="60b37-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="60b37-125">Después de ejecuta este comando, Skype para Business Server depurará todos los registros de archivado más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="60b37-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="60b37-126">El siguiente comando limita la purga de los registros archivados que se han exportado a un archivo de datos (con el cmdlet **Export-CSArchivingData**).</span><span class="sxs-lookup"><span data-stu-id="60b37-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="60b37-127">Es preciso que también establezca el parámetro PurgeExportedArchivesOnly en True ($True).</span><span class="sxs-lookup"><span data-stu-id="60b37-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="60b37-128">Después de ejecuta este comando, Skype para Business Server depurará sólo los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para el parámetro KeepArchivingDataForDays; y, 2) se hayan exportado mediante el cmdlet **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="60b37-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="60b37-129">Para deshabilitar la purga automatizada de los registros de archivado, establezca el parámetro EnablePurging en False ($False):</span><span class="sxs-lookup"><span data-stu-id="60b37-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="60b37-130">En el ejemplo siguiente se usa el cmdlet **Invoke-CsArchivingDatabasePurge** para purgar todos los registros de más de 24 horas de antigüedad de la base de datos de archivado en atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="60b37-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="60b37-131">Para asegurarse de que se eliminan todos los registros, incluidos los registros que no se han exportado, el parámetro PurgeExportedArchivesOnly se establece en False ($False).</span><span class="sxs-lookup"><span data-stu-id="60b37-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
