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
# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportar datos archivados desde Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

No se podrán realizar búsquedas ni estarán en un formato legible los datos archivados en las bases de datos de archivado, pero se puede usar el cmdlet Export-CsArchivingData para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML)(EML). Para obtener información detallada acerca de cómo exportar datos archivados, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) en la documentación referente a las operaciones.

Si habilita la integración de Microsoft Exchange, los datos se archivan en los almacenes 2013 de Exchange. Los datos archivados en Exchange 2013 son buscables y detectables. Para obtener más información sobre la compatibilidad con las comunicaciones integradas de Exchange 2013 y Lync Server 2013, consulte [Exchange Server and SharePoint Integration support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación sobre compatibilidad. Para obtener más información sobre cómo obtener acceso a los datos archivados en Exchange, consulte la documentación de Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportación de datos de archivado con los cmdlets de Windows PowerShell

Los datos de archivado se pueden exportar con el cmdlet Export-CSArchivingData. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

**Para exportar datos de archivado**

  - Este comando exporta todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.litwareinc.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C: \\ ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Para exportar datos de archivado para un solo usuario**

  - El comando siguiente permite exportar datos de archivado para un usuario individual: kenmyer@litwareinc.com. Esto se lleva a cabo mediante la inclusión del parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Compatibilidad con la integración de Exchange Server y SharePoint en Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

