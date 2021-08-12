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
ms.openlocfilehash: bb23861ea7615584de3ce6247f7281d94b5c60853767aaaa6ae495d3a6264dc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311088"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar datos archivados en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo exportar datos archivados para Skype Empresarial Server.
  
Los datos archivados en bases de datos de archivado no se pueden buscar o en un formato legible, pero puede usar el cmdlet **Export-CsArchivingData** para extraer registros de la base de datos y guardarlos como un archivo de correo electrónico (EML) de Outlook.
  
Si habilita la integración Exchange Microsoft, los datos se archivarán en Exchange almacenes. Los datos archivados Exchange pueden buscarse y detectarse. Para obtener más información sobre cómo obtener acceso a los datos que se archivan en Exchange, consulte la Exchange documentación.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar datos de archivado mediante Windows PowerShell cmdlets

Puede exportar datos archivados mediante el cmdlet Export-CSArchivingData archivo. 
  
El siguiente comando exporta todos los datos de archivado escritos en la base de datos atl-sql-001.contoso.com desde el 1 de junio de 2012. El archivo de salida resultante se almacenará en la carpeta C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

El siguiente comando exporta datos de archivado para un único usuario: kenmyer@contoso.com. Para ello, se incluye el parámetro UserUri seguido de la dirección SIP del usuario. Por ejemplo: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obtener más información, vea el tema de ayuda del cmdlet [Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
