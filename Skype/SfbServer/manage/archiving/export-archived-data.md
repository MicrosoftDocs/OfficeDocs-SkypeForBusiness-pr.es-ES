---
title: Exportar datos archivados en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: Obtenga información sobre cómo exportar datos archivados de Skype para Business Server.'
ms.openlocfilehash: 7def9d2ea287c95695784161db72937ff4f2d5a4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890125"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="d61be-103">Exportar datos archivados en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d61be-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="d61be-104">**Resumen:** Obtenga información sobre cómo exportar datos archivados de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d61be-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="d61be-105">Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="d61be-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="d61be-106">Si habilita la integración de Microsoft Exchange, se archivan datos en almacenes de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d61be-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="d61be-107">Datos archivados de Exchange están que admite búsquedas y que se pueda detectar.</span><span class="sxs-lookup"><span data-stu-id="d61be-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="d61be-108">Para obtener información detallada acerca del acceso a datos que se archivan en Exchange, consulte la documentación de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d61be-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d61be-109">Exportación de datos de archivado mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d61be-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d61be-110">Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d61be-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="d61be-p102">El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="d61be-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="d61be-113">El siguiente comando permite exportar datos de archivado para un usuario individual: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d61be-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="d61be-114">Esto se realiza mediante la inclusión del parámetro UserUri seguido de dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="d61be-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="d61be-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d61be-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="d61be-116">Para obtener más información, vea el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d61be-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

