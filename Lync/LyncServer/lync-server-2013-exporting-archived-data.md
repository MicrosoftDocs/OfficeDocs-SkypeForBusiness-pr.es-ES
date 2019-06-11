---
title: 'Lync Server 2013: exportación de datos archivados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportar datos archivados desde Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet Export-CsArchivingData para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML). Para obtener más información sobre cómo exportar datos archivados, consulte [exportar-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) en la documentación de operaciones.

Si habilita la integración de Microsoft Exchange, los datos se archivarán en los almacenes 2013 de Exchange. Los datos archivados en Exchange 2013 se pueden buscar y detectar. Para obtener más información sobre la compatibilidad de las comunicaciones integradas para Exchange 2013 y Lync Server 2013, consulte compatibilidad de la [integración de Exchange Server y SharePoint en Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación de soporte técnico. Para obtener más información sobre cómo obtener acceso a datos archivados en Exchange, consulte la documentación de Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar datos de archivado mediante cmdlets de Windows PowerShell

El archivado de datos se puede exportar mediante el cmdlet Export-CSArchivingData. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

**Para exportar datos de archivado**

  - Este comando exporta todos los datos de archivado escritos en la base de datos de archivado atl-sql-001.litwareinc.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C\\: ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Exportar datos de archivado para un único usuario**

  - El siguiente comando exporta datos de archivado para un solo usuario: kenmyer@litwareinc.com. Esto se lleva a cabo con la inclusión del parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Exportar-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

