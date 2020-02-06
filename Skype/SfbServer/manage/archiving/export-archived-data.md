---
title: Exportar datos archivados en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: Aprenda a exportar datos archivados para Skype empresarial Server.'
ms.openlocfilehash: 12ba59ff11a988fd95eb2207cd826a4399db2779
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818912"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="e291f-103">Exportar datos archivados en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e291f-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="e291f-104">**Resumen:** Aprenda a exportar datos archivados para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e291f-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="e291f-105">Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="e291f-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="e291f-106">Si habilita la integración de Microsoft Exchange, los datos se archivan en los almacenes de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e291f-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="e291f-107">Los datos archivados en Exchange se pueden buscar y detectar.</span><span class="sxs-lookup"><span data-stu-id="e291f-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="e291f-108">Para obtener más información sobre cómo obtener acceso a datos archivados en Exchange, consulte la documentación de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e291f-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e291f-109">Exportar datos de archivado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e291f-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e291f-110">Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e291f-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="e291f-p102">El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="e291f-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="e291f-113">El siguiente comando permite exportar datos de archivado para un usuario individual: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e291f-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="e291f-114">Esto se realiza incluyendo el parámetro UserUri seguido de la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="e291f-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="e291f-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e291f-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="e291f-116">Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e291f-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

