---
title: Instalar almacén de configuración local (invocar) (configurar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para iniciar la instalación de la base de datos que contendrán la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios. Para un equipo que se encuentra en la red interna de la organización, selecciona Recuperar configuración automáticamente desde el Almacén de administración central.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827210"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="9f783-104">Instalar almacén de configuración local (invocar) (configurar)</span><span class="sxs-lookup"><span data-stu-id="9f783-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="9f783-105">Para iniciar la instalación de la base de datos que contendrán la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios.</span><span class="sxs-lookup"><span data-stu-id="9f783-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="9f783-106">Para un equipo que se encuentra en la red interna de la organización, seleccione Recuperar configuración **automáticamente desde el Almacén de administración central.**</span><span class="sxs-lookup"><span data-stu-id="9f783-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="9f783-107">Si va a instalar una réplica del almacén de administración central en un servidor perimetral, necesita seleccionar que se lea la copia exportada del documento de configuración en el medio portátil, por ejemplo una unidad Flash USB, una unidad de disco duro USB, un CD-ROM, etcétera.</span><span class="sxs-lookup"><span data-stu-id="9f783-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9f783-108">Si va a instalar el almacén de configuración local en un servidor perimetral, la información de configuración debe estar en un formato exportado desde el almacén de administración central ejecutando el cmdlet Windows PowerShell local:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="9f783-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="9f783-109">Tras haber seleccionado la opción pertinente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9f783-109">After you have selected the appropriate option, click **Next**.</span></span>
  

