---
title: Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumen: Conozca cómo hacer copia de seguridad y restaurar bases de datos de servidor de charla persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a hacer copia de seguridad y restaurar bases de datos de servidor de charla persistente en Skype para Business Server 2015.
  
Servidor de charla persistente requiere software de base de datos de SQL Server para almacenar datos de salón de chat, como historial y contenido, configuración, aprovisionamiento de usuarios y otros metadatos relevantes. Además, si su organización tiene normas que requieren la actividad de Chat persistentes se almacenen y se habilita el servicio opcional de cumplimiento de normas, software de base de datos de SQL Server se utiliza para almacenar datos de cumplimiento de normas, incluido contenido de chat y eventos, como incorporación y el cese de las habitaciones. Contenido de salón de chat se almacena en la base de datos persistente Chat (CGM). Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp). Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular. 
  
## <a name="back-up-the-databases"></a>Hacer una copia de seguridad de las bases de datos

Hay dos maneras de copia de datos persistente de charla. 
  
- Copia de seguridad de SQL Server
    
- El cmdlet **Export-CsPersistentChatData** , que exporta datos de Chat persistentes como un archivo
    
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

Cómo restaurar los datos persistentes de charla depende del método que utilizó para la copia de seguridad. Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server. Si utiliza el cmdlet **Export-CsPersistentChatData** para copiar los datos persistentes de charla, debe utilizar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

o
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


