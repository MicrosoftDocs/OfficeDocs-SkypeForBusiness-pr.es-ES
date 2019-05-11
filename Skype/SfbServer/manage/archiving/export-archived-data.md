---
title: Exportar datos archivados en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: Obtenga información sobre cómo exportar datos archivados de Skype para Business Server.'
ms.openlocfilehash: fd17fda9d36c5739d9d1cab7845921a442a4155d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884974"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar datos archivados en Skype para Business Server

**Resumen:** Obtenga información sobre cómo exportar datos archivados de Skype para Business Server.
  
Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).
  
Si habilita la integración de Microsoft Exchange, se archivan datos en almacenes de Exchange. Datos archivados de Exchange están que admite búsquedas y que se pueda detectar. Para obtener información detallada acerca del acceso a datos que se archivan en Exchange, consulte la documentación de Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportación de datos de archivado mediante el uso de Cmdlets de Windows PowerShell

Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet. 
  
El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

El siguiente comando permite exportar datos de archivado para un usuario individual: kenmyer@contoso.com. Esto se realiza mediante la inclusión del parámetro UserUri seguido de dirección SIP del usuario. Por ejemplo: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obtener más información, vea el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

