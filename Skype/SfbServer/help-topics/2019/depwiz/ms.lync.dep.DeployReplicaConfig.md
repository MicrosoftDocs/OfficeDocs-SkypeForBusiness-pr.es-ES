---
title: Instalar invocación de almacén de configuración local (configurar)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio. Para un equipo que se encuentra en la red interna de la organización, seleccione recuperar la configuración automáticamente en el almacén de Administración Central.
ms.openlocfilehash: 21cf742be33ab79daa733cbc52aa557b6ccee145
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886271"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="a56af-104">Instalar invocación de almacén de configuración local (configurar)</span><span class="sxs-lookup"><span data-stu-id="a56af-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="a56af-105">Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio.</span><span class="sxs-lookup"><span data-stu-id="a56af-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="a56af-106">Para un equipo que se encuentra en la red interna de la organización, seleccione **recuperar la configuración automáticamente el almacén de Administración Central**.</span><span class="sxs-lookup"><span data-stu-id="a56af-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="a56af-107">Si va a instalar una réplica del almacén de Administración Central en un servidor perimetral, seleccione para leer la copia del documento de configuración exportada desde los medios portátiles, como una unidad flash USB, unidad de disco duro USB, CD-ROM u otros medios.</span><span class="sxs-lookup"><span data-stu-id="a56af-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a56af-108">Si va a instalar el almacén de configuración Local en un servidor perimetral, la información de configuración debe estar en un formato que se han exportado desde la Administración Central almacén ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="a56af-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="a56af-109">Después de haber seleccionado la opción adecuada, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a56af-109">After you have selected the appropriate option, click **Next**.</span></span>
  

