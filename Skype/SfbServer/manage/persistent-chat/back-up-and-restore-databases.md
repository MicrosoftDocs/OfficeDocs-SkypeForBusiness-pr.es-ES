---
title: Copia de seguridad y restauración de bases de datos de chat persistente Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumen: obtenga información sobre cómo hacer una copia de seguridad y restaurar bases de datos del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: eb6b7e005691abda351993e716ba43a137ffa28c17f7fc9e6297a7e1373f9ad7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281713"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Copia de seguridad y restauración de bases de datos de chat persistente Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo hacer una copia de seguridad y restaurar bases de datos del servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente requiere SQL Server de base de datos para almacenar datos del salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes. Además, si su organización tiene normativas que requieren que se archive la actividad de chat persistente y el servicio de cumplimiento opcional está habilitado, se usa un software de base de datos SQL Server para almacenar datos de cumplimiento, incluidos el contenido y los eventos de chat, como la unión y la salida de salas. El contenido del salón de chat se almacena en la base de datos de chat persistente (mgc). Los datos de cumplimiento se almacenan en la base de datos de cumplimiento (mgccomp). Se trata de datos críticos para el negocio que deben realizarse con regularidad. 
  
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 

## <a name="back-up-the-databases"></a>Copia de seguridad de las bases de datos

Hay dos formas de hacer una copia de seguridad de los datos de chat persistente. 
  
- SQL Server Copia de seguridad
    
- El cmdlet **Export-CsPersistentChatData,** que exporta datos de chat persistente como un archivo
    
Los datos creados mediante una copia de seguridad de SQL Server requieren mucho más espacio en disco (posiblemente 20 veces más) que los creados por el cmdlet **Export-CsPersistentChatData,** pero es probable que una copia de seguridad de SQL Server sea un procedimiento con el que esté familiarizado.
  
Si desea usar SQL Server de copia de seguridad, consulte la SQL para obtener más información. 
  
Si desea usar el cmdlet **Export-CsPersistentChatData,** puede especificar el comando de la siguiente manera:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por ejemplo, el siguiente comando exporta datos de chat persistente de la base de datos de chat persistente ubicada en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Dado que no se especificó el parámetro Level, el comando realizará una exportación completa de la información de chat persistente:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurar las bases de datos

La forma de restaurar los datos de chat persistente depende del método que usó para hacer una copia de seguridad de los datos. Si usó SQL Server de copia de seguridad, debe usar SQL Server procedimientos de restauración. Si usó el cmdlet **Export-CsPersistentChatData** para realizar una copia de seguridad de los datos de chat persistente, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
