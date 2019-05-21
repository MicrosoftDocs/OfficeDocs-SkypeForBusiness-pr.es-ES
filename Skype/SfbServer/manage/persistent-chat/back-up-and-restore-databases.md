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
ms.openlocfilehash: 07d904620bbc5925ec6457924af6ee1e48d98d55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279364"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="c1dd4-103">Realizar una copia de seguridad y restaurar las bases de datos del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c1dd4-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c1dd4-104">**Resumen:** Aprenda a realizar copias de seguridad y restaurar bases de datos de servidores de chat persistentes en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c1dd4-105">El servidor de chat persistente requiere que el software de base de datos de SQL Server almacene los datos del salón de chat, como el historial y el contenido, la configuración, el aprovisionamiento de usuarios y otros metadatos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="c1dd4-106">Además, si su organización tiene normativas que requieren una actividad de chat persistente para archivarse y el servicio opcional de cumplimiento está habilitado, el software de base de datos de SQL Server se usa para almacenar datos de cumplimiento, incluidos los eventos y el contenido de chat, como unirse y salir de las salas.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="c1dd4-107">El contenido del salón de chat se almacena en la base de datos de chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="c1dd4-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="c1dd4-108">Los datos de cumplimiento normativo se almacenan en la base de datos de cumplimiento normativo (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="c1dd4-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="c1dd4-109">Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c1dd4-110">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c1dd4-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="c1dd4-112">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="c1dd4-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="c1dd4-113">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="c1dd4-114">Hacer una copia de seguridad de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="c1dd4-114">Back up the databases</span></span>

<span data-ttu-id="c1dd4-115">Existen dos formas de realizar copias de seguridad de datos persistentes del chat.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="c1dd4-116">Copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1dd4-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="c1dd4-117">El cmdlet **Export-CsPersistentChatData** , que exporta datos de chat persistentes como un archivo</span><span class="sxs-lookup"><span data-stu-id="c1dd4-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="c1dd4-118">Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con el cmdlet **Export-CsPersistentChatData**, la copia de seguridad de SQL Server es, posiblemente, un procedimiento que le será familiar.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="c1dd4-119">Si desea utilizar los procedimientos de copia de seguridad de SQL Server, consulte la documentación de SQL para más información.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="c1dd4-120">Si desea utilizar el cmdlet **Export-CsPersistentChatData**, puede especificar el comando de esta forma:</span><span class="sxs-lookup"><span data-stu-id="c1dd4-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="c1dd4-121">o</span><span class="sxs-lookup"><span data-stu-id="c1dd4-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="c1dd4-p103">Por ejemplo, el siguiente comando exporta los datos del chat persistente de la base de datos del chat persistente en el servidor atl-sql-001.contoso.com; los datos exportados se almacenarán en el archivo C:\Logs\PersistentChatData.zip. Puesto que no se ha especificado el parámetro Level, el comando hará una exportación completa de la información del chat persistente:</span><span class="sxs-lookup"><span data-stu-id="c1dd4-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="c1dd4-124">Restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="c1dd4-124">Restore the databases</span></span>

<span data-ttu-id="c1dd4-125">La manera en que se restauran los datos del chat persistente depende del método que usó para realizar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="c1dd4-126">Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c1dd4-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="c1dd4-127">Si usó el cmdlet **Export-CsPersistentChatData** para realizar copias de seguridad de datos de chat persistentes, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos:</span><span class="sxs-lookup"><span data-stu-id="c1dd4-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="c1dd4-128">o</span><span class="sxs-lookup"><span data-stu-id="c1dd4-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
