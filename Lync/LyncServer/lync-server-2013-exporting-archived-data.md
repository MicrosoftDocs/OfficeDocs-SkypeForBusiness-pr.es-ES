---
title: 'Lync Server 2013: exportar datos archivados'
description: 'Lync Server 2013: exportar datos archivados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656751f1a2d03b50f0c938a8501ba3e95e304cff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564756"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="46bb9-103">Exportar datos archivados desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46bb9-103">Exporting archived data from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46bb9-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="46bb9-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="46bb9-105">No se podrán realizar búsquedas ni estarán en un formato legible los datos archivados en las bases de datos de archivado, pero se puede usar el cmdlet Export-CsArchivingData para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML)(EML).</span><span class="sxs-lookup"><span data-stu-id="46bb9-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="46bb9-106">Para obtener información detallada acerca de cómo exportar datos archivados, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) en la documentación referente a las operaciones.</span><span class="sxs-lookup"><span data-stu-id="46bb9-106">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="46bb9-107">Si habilita la integración de Microsoft Exchange, los datos se archivan en los almacenes 2013 de Exchange.</span><span class="sxs-lookup"><span data-stu-id="46bb9-107">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="46bb9-108">Los datos archivados en Exchange 2013 son buscables y detectables.</span><span class="sxs-lookup"><span data-stu-id="46bb9-108">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="46bb9-109">Para obtener más información sobre la compatibilidad con las comunicaciones integradas de Exchange 2013 y Lync Server 2013, consulte [Exchange Server and SharePoint Integration support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="46bb9-109">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="46bb9-110">Para obtener más información sobre cómo obtener acceso a los datos archivados en Exchange, consulte la documentación de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="46bb9-110">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="46bb9-111">Exportación de datos de archivado con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46bb9-111">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="46bb9-112">Los datos de archivado se pueden exportar con el cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="46bb9-112">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="46bb9-113">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46bb9-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="46bb9-114">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="46bb9-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="46bb9-115">**Para exportar datos de archivado**</span><span class="sxs-lookup"><span data-stu-id="46bb9-115">**To export archiving data**</span></span>

  - <span data-ttu-id="46bb9-116">Este comando exporta todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.litwareinc.com desde el 1 de junio de 2012.</span><span class="sxs-lookup"><span data-stu-id="46bb9-116">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="46bb9-117">El archivo de salida resultante se almacenará en la carpeta C: \\ ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="46bb9-117">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="46bb9-118">**Para exportar datos de archivado para un solo usuario**</span><span class="sxs-lookup"><span data-stu-id="46bb9-118">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="46bb9-p105">El comando siguiente permite exportar datos de archivado para un usuario individual: kenmyer@litwareinc.com. Esto se lleva a cabo mediante la inclusión del parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46bb9-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="46bb9-122">Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="46bb9-122">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46bb9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46bb9-123">See Also</span></span>


[<span data-ttu-id="46bb9-124">Compatibilidad con la integración de Exchange Server y SharePoint en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46bb9-124">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="46bb9-125">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="46bb9-125">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="46bb9-126">Administración de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46bb9-126">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

