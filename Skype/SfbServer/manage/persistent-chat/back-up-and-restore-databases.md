---
title: Copia de seguridad y restauración de bases de datos de chat persistente en Skype Empresarial Server 2015
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
description: 'Resumen: obtenga información sobre cómo hacer copias de seguridad y restaurar bases de datos del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826380"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Copia de seguridad y restauración de bases de datos de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo hacer copias de seguridad y restaurar bases de datos del servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente SQL Server software de base de datos para almacenar datos de salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes. Además, si su organización tiene normativas que requieren que se archive la actividad de chat persistente y el servicio de cumplimiento opcional está habilitado SQL Server, se usa un software de base de datos para almacenar datos de cumplimiento, incluido el contenido y los eventos de chat, como la unión y salida de salas. El contenido del salón de chat se almacena en la base de datos de chat persistente (mgc). Los datos de cumplimiento se almacenan en la base de datos de cumplimiento (mgccomp). Se trata de datos fundamentales para la empresa de los que se debe realizar una copia de seguridad periódicamente. 
  
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

## <a name="back-up-the-databases"></a>Copia de seguridad de las bases de datos

Hay dos formas de hacer una copia de seguridad de los datos de chat persistente. 
  
- SQL Server copia de seguridad
    
- El cmdlet **Export-CsPersistentChatData,** que exporta datos de chat persistente como un archivo
    
Los datos que se crean mediante una copia de seguridad de SQL Server requieren bastante más espacio en disco (posiblemente 20 veces más) que los creados por el cmdlet **Export-CsPersistentChatData,** pero es probable que una copia de seguridad de SQL Server sea un procedimiento con el que esté familiarizado.
  
Si desea usar procedimientos de copia SQL Server copia de seguridad, consulte la documentación SQL para obtener más información. 
  
Si desea usar el cmdlet **Export-CsPersistentChatData,** puede especificar el comando de la siguiente manera:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por ejemplo, el siguiente comando exporta datos de chat persistente de la base de datos de chat persistente ubicada en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Como no se especificó el parámetro Level, el comando realizará una exportación completa de la información de chat persistente:
  
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
