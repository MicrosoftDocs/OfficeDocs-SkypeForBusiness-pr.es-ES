---
title: Exportar datos archivados de Lync Server 2013
TOCTitle: Exportar datos archivados de Lync Server 2013
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48274361
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportar datos archivados de Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

No se podrán realizar búsquedas ni estarán en un formato legible los datos archivados en las bases de datos de archivado, pero se puede usar el cmdlet Export-CsArchivingData para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML)(EML). Para obtener información detallada acerca de cómo exportar datos archivados, consulte [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) en la documentación referente a las operaciones.

Si habilita la integración con Microsoft Exchange, los datos se archivan en Exchange 2013. Se pueden realizar búsquedas y reconocer los datos almacenados en Exchange 2013. Para obtener más detalles acerca de la compatibilidad para las comunicaciones integradas de Exchange 2013 y Lync Server 2013, vea [Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación referente a la compatibilidad. Para obtener información detallada acera de cómo tener acceso a los datos archivados en Exchange, consulte la documentación de Exchange 2013.

## Exportación de los datos de archivado con los cmdlets del Shell de administración de Lync Server

Los datos de archivado se pueden exportar con el cmdlet Export-CSArchivingData. Dicho cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

**Exportación de datos de archivado**

  - Este comando exporta todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.litwareinc.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\\ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Exportación de datos de archivado para un usuario individual**

  - El comando siguiente permite exportar datos de archivado para un usuario individual: kenmyer@litwareinc.com. Esto se lleva a cabo mediante la inclusión del parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Para más información, vea el tema de ayuda del cmdlet [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData).

## Vea también

#### Conceptos

[Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### Otros recursos

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)

