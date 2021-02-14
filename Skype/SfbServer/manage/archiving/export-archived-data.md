---
title: Exportar datos archivados en Skype Empresarial Server
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
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: obtenga información sobre cómo exportar datos archivados para Skype Empresarial Server.'
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817570"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="de49e-103">Exportar datos archivados en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="de49e-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="de49e-104">**Resumen:** Obtenga información sobre cómo exportar datos archivados para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="de49e-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="de49e-105">Los datos archivados en bases de datos de archivado no se pueden buscar o en un formato legible, pero puede usar el cmdlet **Export-CsArchivingData** para extraer registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="de49e-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="de49e-106">Si habilita la integración de Microsoft Exchange, los datos se archivan en almacenes de Exchange.</span><span class="sxs-lookup"><span data-stu-id="de49e-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="de49e-107">Los datos archivados en Exchange se pueden buscar y detectar.</span><span class="sxs-lookup"><span data-stu-id="de49e-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="de49e-108">Para obtener más información sobre cómo obtener acceso a los datos archivados en Exchange, consulte la documentación de Exchange.</span><span class="sxs-lookup"><span data-stu-id="de49e-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de49e-109">Exportación de datos de archivado mediante cmdlets Windows PowerShell datos</span><span class="sxs-lookup"><span data-stu-id="de49e-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="de49e-110">Puede exportar datos archivados con el cmdlet Export-CSArchivingData archivo.</span><span class="sxs-lookup"><span data-stu-id="de49e-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="de49e-111">El siguiente comando exporta todos los datos de archivado escritos en la base de datos atl-sql-001.contoso.com desde el 1 de junio de 2012.</span><span class="sxs-lookup"><span data-stu-id="de49e-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="de49e-112">El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="de49e-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="de49e-113">El siguiente comando exporta los datos de archivado de un solo usuario: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="de49e-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="de49e-114">Para ello, se incluye el parámetro UserUri seguido de la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="de49e-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="de49e-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de49e-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="de49e-116">Para obtener más información, consulte el tema de ayuda del cmdlet [Export-CsArchivingData.](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="de49e-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

