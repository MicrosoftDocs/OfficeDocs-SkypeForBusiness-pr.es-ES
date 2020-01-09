---
title: Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumen: Aprenda a realizar copias de seguridad y restaurar bases de datos de servidores de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: a8c407c35b9d864889c26cbea7296dbed86516fa
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991975"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a realizar copias de seguridad y restaurar bases de datos de servidores de chat persistentes en Skype empresarial Server 2015.
  
El servidor de chat persistente requiere que el software de base de datos de SQL Server almacene los datos del salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes. Además, si su organización tiene normativas que requieren una actividad de chat persistente para archivarse y el servicio opcional de cumplimiento está habilitado, el software de base de datos de SQL Server se usa para almacenar datos de cumplimiento, incluidos los eventos y el contenido de chat, como unirse y salir de las salas. El contenido del salón de chat se almacena en la base de datos de chat persistente (MGC). Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp). Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular. 
  
> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 

## <a name="back-up-the-databases"></a>Hacer una copia de seguridad de las bases de datos

Existen dos formas de realizar copias de seguridad de datos persistentes del chat. 
  
- Copia de seguridad de SQL Server
    
- El cmdlet **Export-CsPersistentChatData** , que exporta datos de chat persistentes como un archivo
    
Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con el cmdlet **Export-CsPersistentChatData**, la copia de seguridad de SQL Server es, posiblemente, un procedimiento que le será familiar.
  
Si desea utilizar los procedimientos de copia de seguridad de SQL Server, consulte la documentación de SQL para más información. 
  
Si desea utilizar el cmdlet **Export-CsPersistentChatData**, puede especificar el comando de esta forma:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

o
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por ejemplo, el siguiente comando exporta los datos del chat persistente de la base de datos del chat persistente en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Puesto que no se ha especificado el parámetro Level, el comando hará una exportación completa de la información del chat persistente:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurar las bases de datos

La manera en que se restauran los datos del chat persistente depende del método que usó para realizar la copia de seguridad. Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server. Si usó el cmdlet **Export-CsPersistentChatData** para realizar copias de seguridad de datos de chat persistentes, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
