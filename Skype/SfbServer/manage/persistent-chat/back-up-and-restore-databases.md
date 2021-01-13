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
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="f94d4-103">Copia de seguridad y restauración de bases de datos de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f94d4-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f94d4-104">**Resumen:** Obtenga información sobre cómo hacer copias de seguridad y restaurar bases de datos del servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f94d4-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f94d4-105">El servidor de chat persistente SQL Server software de base de datos para almacenar datos de salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes.</span><span class="sxs-lookup"><span data-stu-id="f94d4-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="f94d4-106">Además, si su organización tiene normativas que requieren que se archive la actividad de chat persistente y el servicio de cumplimiento opcional está habilitado SQL Server, se usa un software de base de datos para almacenar datos de cumplimiento, incluido el contenido y los eventos de chat, como la unión y salida de salas.</span><span class="sxs-lookup"><span data-stu-id="f94d4-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="f94d4-107">El contenido del salón de chat se almacena en la base de datos de chat persistente (mgc).</span><span class="sxs-lookup"><span data-stu-id="f94d4-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="f94d4-108">Los datos de cumplimiento se almacenan en la base de datos de cumplimiento (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="f94d4-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="f94d4-109">Se trata de datos fundamentales para la empresa de los que se debe realizar una copia de seguridad periódicamente.</span><span class="sxs-lookup"><span data-stu-id="f94d4-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f94d4-110">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f94d4-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f94d4-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="f94d4-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="f94d4-112">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="f94d4-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="f94d4-113">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f94d4-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="f94d4-114">Copia de seguridad de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="f94d4-114">Back up the databases</span></span>

<span data-ttu-id="f94d4-115">Hay dos formas de hacer una copia de seguridad de los datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f94d4-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="f94d4-116">SQL Server copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f94d4-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="f94d4-117">El cmdlet **Export-CsPersistentChatData,** que exporta datos de chat persistente como un archivo</span><span class="sxs-lookup"><span data-stu-id="f94d4-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="f94d4-118">Los datos que se crean mediante una copia de seguridad de SQL Server requieren bastante más espacio en disco (posiblemente 20 veces más) que los creados por el cmdlet **Export-CsPersistentChatData,** pero es probable que una copia de seguridad de SQL Server sea un procedimiento con el que esté familiarizado.</span><span class="sxs-lookup"><span data-stu-id="f94d4-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="f94d4-119">Si desea usar procedimientos de copia SQL Server copia de seguridad, consulte la documentación SQL para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f94d4-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="f94d4-120">Si desea usar el cmdlet **Export-CsPersistentChatData,** puede especificar el comando de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f94d4-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="f94d4-121">o</span><span class="sxs-lookup"><span data-stu-id="f94d4-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="f94d4-122">Por ejemplo, el siguiente comando exporta datos de chat persistente de la base de datos de chat persistente ubicada en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="f94d4-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="f94d4-123">Como no se especificó el parámetro Level, el comando realizará una exportación completa de la información de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="f94d4-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="f94d4-124">Restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="f94d4-124">Restore the databases</span></span>

<span data-ttu-id="f94d4-125">La forma de restaurar los datos de chat persistente depende del método que usó para hacer una copia de seguridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="f94d4-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="f94d4-126">Si usó SQL Server de copia de seguridad, debe usar SQL Server procedimientos de restauración.</span><span class="sxs-lookup"><span data-stu-id="f94d4-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="f94d4-127">Si usó el cmdlet **Export-CsPersistentChatData** para realizar una copia de seguridad de los datos de chat persistente, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:</span><span class="sxs-lookup"><span data-stu-id="f94d4-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="f94d4-128">o</span><span class="sxs-lookup"><span data-stu-id="f94d4-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
