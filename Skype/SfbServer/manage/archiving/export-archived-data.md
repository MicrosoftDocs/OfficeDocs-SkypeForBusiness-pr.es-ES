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
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>Exportar datos archivados en Skype Empresarial Server 2015

**Resumen:** Aprenda a exportar los datos archivados de Skype para Business Server 2015.
  
Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).
  
Si habilita la integración de Microsoft Exchange, se archivan los datos en los almacenes de Exchange. Datos archivados en Exchange están que se puede buscar e intuitivo. Para obtener más información acerca del acceso a datos archivados en Exchange, consulte la documentación de Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar datos de Archiving mediante Cmdlets de Windows PowerShell

Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet. 
  
El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

El siguiente comando exporta archiving de datos para un único usuario: kenmyer@contoso.com. Esto se hace incluyendo el parámetro UserUri, seguido de la dirección del usuario SIP. Por ejemplo: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obtener más información, vea el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

