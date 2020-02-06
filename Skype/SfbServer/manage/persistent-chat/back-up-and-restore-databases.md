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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumen: Aprenda a realizar copias de seguridad y restaurar bases de datos de servidores de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817346"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="5d8ec-103">Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d8ec-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d8ec-104">**Resumen:** Aprenda a realizar copias de seguridad y restaurar bases de datos de servidores de chat persistentes en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5d8ec-105">El servidor de chat persistente requiere que el software de base de datos de SQL Server almacene los datos del salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="5d8ec-106">Además, si su organización tiene normativas que requieren una actividad de chat persistente para archivarse y el servicio opcional de cumplimiento está habilitado, el software de base de datos de SQL Server se usa para almacenar datos de cumplimiento, incluidos los eventos y el contenido de chat, como unirse y salir de las salas.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="5d8ec-107">El contenido del salón de chat se almacena en la base de datos de chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="5d8ec-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="5d8ec-108">Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="5d8ec-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="5d8ec-109">Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5d8ec-110">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5d8ec-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="5d8ec-112">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="5d8ec-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="5d8ec-113">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="5d8ec-114">Hacer una copia de seguridad de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="5d8ec-114">Back up the databases</span></span>

<span data-ttu-id="5d8ec-115">Existen dos formas de realizar copias de seguridad de datos persistentes del chat.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="5d8ec-116">Copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d8ec-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="5d8ec-117">El cmdlet **Export-CsPersistentChatData** , que exporta datos de chat persistentes como un archivo</span><span class="sxs-lookup"><span data-stu-id="5d8ec-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="5d8ec-118">Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con el cmdlet **Export-CsPersistentChatData**, la copia de seguridad de SQL Server es, posiblemente, un procedimiento que le será familiar.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="5d8ec-119">Si desea utilizar los procedimientos de copia de seguridad de SQL Server, consulte la documentación de SQL para más información.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="5d8ec-120">Si desea utilizar el cmdlet **Export-CsPersistentChatData**, puede especificar el comando de esta forma:</span><span class="sxs-lookup"><span data-stu-id="5d8ec-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="5d8ec-121">o</span><span class="sxs-lookup"><span data-stu-id="5d8ec-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="5d8ec-p103">Por ejemplo, el siguiente comando exporta los datos del chat persistente de la base de datos del chat persistente en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Puesto que no se ha especificado el parámetro Level, el comando hará una exportación completa de la información del chat persistente:</span><span class="sxs-lookup"><span data-stu-id="5d8ec-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="5d8ec-124">Restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="5d8ec-124">Restore the databases</span></span>

<span data-ttu-id="5d8ec-125">La manera en que se restauran los datos del chat persistente depende del método que usó para realizar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="5d8ec-126">Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d8ec-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="5d8ec-127">Si usó el cmdlet **Export-CsPersistentChatData** para realizar copias de seguridad de datos de chat persistentes, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:</span><span class="sxs-lookup"><span data-stu-id="5d8ec-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="5d8ec-128">o</span><span class="sxs-lookup"><span data-stu-id="5d8ec-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
