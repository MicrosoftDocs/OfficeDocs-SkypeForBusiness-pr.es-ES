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
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar datos archivados en Skype empresarial Server

**Resumen:** Aprenda a exportar datos archivados para Skype empresarial Server.
  
Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).
  
Si habilita la integración de Microsoft Exchange, los datos se archivan en los almacenes de Exchange. Los datos archivados en Exchange se pueden buscar y detectar. Para obtener más información sobre cómo obtener acceso a datos archivados en Exchange, consulte la documentación de Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar datos de archivado mediante cmdlets de Windows PowerShell

Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet. 
  
El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

El siguiente comando permite exportar datos de archivado para un usuario individual: kenmyer@contoso.com. Esto se realiza incluyendo el parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

