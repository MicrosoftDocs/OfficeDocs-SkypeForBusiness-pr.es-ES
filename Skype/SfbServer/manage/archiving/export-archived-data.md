---
title: Exportar datos archivados en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumen: Aprenda a exportar datos archivados para Skype empresarial Server.'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286140"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar datos archivados en Skype empresarial Server

**Resumen:** Aprenda a exportar datos archivados para Skype empresarial Server.
  
Los datos archivados en las bases de datos de archivado no podrán someterse a búsquedas ni estarán en un formato legible; pero, puede usar el cmdlet **Export-CsArchivingData** para extraer los registros de la base de datos y guardarlos como un archivo de correo electrónico de Outlook (EML).
  
Si habilita la integración de Microsoft Exchange, los datos se archivan en los almacenes de Exchange. Los datos archivados en Exchange se pueden buscar y detectar. Para obtener más información sobre cómo obtener acceso a datos archivados en Exchange, consulte la documentación de Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar datos de archivado mediante cmdlets de Windows PowerShell

Puede exportar los datos archivados con el cmdlet Export-CSArchivingData cmdlet. 
  
El siguiente comando permite exportar todos los datos de archivado que se escribieron en la base de datos de archivado atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

El siguiente comando permite exportar datos de archivado para un usuario individual: kenmyer@contoso.com. Esto se realiza incluyendo el parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obtener más información, consulte el tema de ayuda para el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

