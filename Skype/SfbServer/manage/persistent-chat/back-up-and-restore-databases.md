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
description: 'Resumen: Información sobre la copia de seguridad y restauración de bases de datos de servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 37a2a1bb2cab33a05468f27e04eda10b927b4bbe
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568741"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="e2340-103">Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2340-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2340-104">**Resumen:** Obtenga información sobre cómo realizar una copia de y restauración de bases de datos de servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e2340-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e2340-105">Persistent Chat Server requiere el software de base de datos de SQL Server para almacenar datos de salón de chat, como historial y contenido, configuración, aprovisionamiento de los usuarios y otros metadatos relevantes.</span><span class="sxs-lookup"><span data-stu-id="e2340-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="e2340-106">Además, si su organización tiene las normativas que requieren la actividad de Chat persistente para ser archivados y está habilitado el servicio opcional de cumplimiento, software de base de datos de SQL Server se usa para almacenar datos de cumplimiento de normas, incluido el contenido de conversaciones y eventos, como unirse a y salir de salas.</span><span class="sxs-lookup"><span data-stu-id="e2340-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="e2340-107">Contenido del salón de chat se almacena en la base de datos de Chat persistente (CGM).</span><span class="sxs-lookup"><span data-stu-id="e2340-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="e2340-108">Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="e2340-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="e2340-109">Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular.</span><span class="sxs-lookup"><span data-stu-id="e2340-109">This is business-critical data that should be backed up regularly.</span></span> 
  
## <a name="back-up-the-databases"></a><span data-ttu-id="e2340-110">Hacer una copia de seguridad de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="e2340-110">Back up the databases</span></span>

<span data-ttu-id="e2340-111">Hay dos formas de realizar copia de seguridad de los datos de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e2340-111">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="e2340-112">Copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2340-112">SQL Server Backup</span></span>
    
- <span data-ttu-id="e2340-113">El cmdlet **Export-CsPersistentChatData** , que exporta datos del Chat persistente como un archivo</span><span class="sxs-lookup"><span data-stu-id="e2340-113">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="e2340-114">Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con el cmdlet **Export-CsPersistentChatData**, la copia de seguridad de SQL Server es, posiblemente, un procedimiento que le será familiar.</span><span class="sxs-lookup"><span data-stu-id="e2340-114">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="e2340-115">Si desea utilizar los procedimientos de copia de seguridad de SQL Server, consulte la documentación de SQL para más información.</span><span class="sxs-lookup"><span data-stu-id="e2340-115">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="e2340-116">Si desea utilizar el cmdlet **Export-CsPersistentChatData**, puede especificar el comando de esta forma:</span><span class="sxs-lookup"><span data-stu-id="e2340-116">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="e2340-117">o</span><span class="sxs-lookup"><span data-stu-id="e2340-117">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="e2340-p102">Por ejemplo, el siguiente comando exporta los datos del chat persistente de la base de datos del chat persistente en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Puesto que no se ha especificado el parámetro Level, el comando hará una exportación completa de la información del chat persistente:</span><span class="sxs-lookup"><span data-stu-id="e2340-p102">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="e2340-120">Restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="e2340-120">Restore the databases</span></span>

<span data-ttu-id="e2340-121">Cómo restaurar los datos de Chat persistente depende el método usado para hacer una copia de.</span><span class="sxs-lookup"><span data-stu-id="e2340-121">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="e2340-122">Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e2340-122">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="e2340-123">Si usa el cmdlet **Export-CsPersistentChatData** para realizar una copia de seguridad de los datos de Chat persistente, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:</span><span class="sxs-lookup"><span data-stu-id="e2340-123">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="e2340-124">o</span><span class="sxs-lookup"><span data-stu-id="e2340-124">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```