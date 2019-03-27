---
title: Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumen: Información sobre la copia de seguridad y restauración de bases de datos de servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: a07321c7e9167e830a7af472e9022b669a45c3e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886426"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo realizar una copia de y restauración de bases de datos de servidor de Chat persistente en Skype para Business Server 2015.
  
Persistent Chat Server requiere el software de base de datos de SQL Server para almacenar datos de salón de chat, como historial y contenido, configuración, aprovisionamiento de los usuarios y otros metadatos relevantes. Además, si su organización tiene las normativas que requieren la actividad de Chat persistente para ser archivados y está habilitado el servicio opcional de cumplimiento, software de base de datos de SQL Server se usa para almacenar datos de cumplimiento de normas, incluido el contenido de conversaciones y eventos, como unirse a y salir de salas. Contenido del salón de chat se almacena en la base de datos de Chat persistente (CGM). Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp). Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular. 
  
> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 

## <a name="back-up-the-databases"></a>Hacer una copia de seguridad de las bases de datos

Hay dos formas de realizar copia de seguridad de los datos de Chat persistente. 
  
- Copia de seguridad de SQL Server
    
- El cmdlet **Export-CsPersistentChatData** , que exporta datos del Chat persistente como un archivo
    
Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con el cmdlet **Export-CsPersistentChatData**, la copia de seguridad de SQL Server es, posiblemente, un procedimiento que le será familiar.
  
Si desea utilizar los procedimientos de copia de seguridad de SQL Server, consulte la documentación de SQL para más información. 
  
Si desea utilizar el cmdlet **Export-CsPersistentChatData**, puede especificar el comando de esta forma:
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por ejemplo, el siguiente comando exporta los datos del chat persistente de la base de datos del chat persistente en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Puesto que no se ha especificado el parámetro Level, el comando hará una exportación completa de la información del chat persistente:
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurar las bases de datos

Cómo restaurar los datos de Chat persistente depende el método usado para hacer una copia de. Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server. Si usa el cmdlet **Export-CsPersistentChatData** para realizar una copia de seguridad de los datos de Chat persistente, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
