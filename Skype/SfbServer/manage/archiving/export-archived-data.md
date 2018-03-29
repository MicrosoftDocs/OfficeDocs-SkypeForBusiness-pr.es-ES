---
title: Exportar datos archivados en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: Conozca cómo exportar los datos archivados de Skype para Business Server 2015.'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="2b703-103">Exportar datos archivados en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b703-103">Export archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="2b703-104">**Resumen:** Aprenda a exportar los datos archivados de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b703-104">**Summary:** Learn how to export archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2b703-105">Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="2b703-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="2b703-106">Si habilita la integración de Microsoft Exchange, se archivan los datos en los almacenes de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b703-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="2b703-107">Datos archivados en Exchange están que se puede buscar e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="2b703-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="2b703-108">Para obtener más información acerca del acceso a datos archivados en Exchange, consulte la documentación de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b703-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b703-109">Exportar datos de Archiving mediante Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b703-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b703-110">Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2b703-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="2b703-p102">El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="2b703-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="2b703-113">El siguiente comando exporta archiving de datos para un único usuario: kenmyer@contoso.com. Esto se hace incluyendo el parámetro UserUri, seguido de la dirección del usuario SIP.</span><span class="sxs-lookup"><span data-stu-id="2b703-113">The following command exports archiving data for a single user: kenmyer@contoso.com. This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="2b703-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b703-114">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="2b703-115">Para obtener más información, vea el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2b703-115">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

