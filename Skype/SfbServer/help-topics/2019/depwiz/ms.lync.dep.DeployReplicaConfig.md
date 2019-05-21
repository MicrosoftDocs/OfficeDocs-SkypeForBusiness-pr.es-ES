---
title: Instalar invocación de almacén de configuración local (configurar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de la base de datos que contendrá la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el generador de topologías del centro de ya instalado y configurado. Almacén de administración o leer la configuración definida de otros elementos multimedia. Para un equipo que se encuentra en la red interna de su organización, seleccione recuperar configuración automáticamente del almacén de administración central.
ms.openlocfilehash: b4249f4968c51fb901e612b2414bb2c6921be40c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303308"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="32a18-104">Instalar invocación de almacén de configuración local (configurar)</span><span class="sxs-lookup"><span data-stu-id="32a18-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="32a18-105">Para comenzar la instalación de la base de datos que contendrá la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el generador de topologías del centro de ya instalado y configurado. Almacén de administración o leer la configuración definida de otros elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="32a18-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="32a18-106">Para un equipo que se encuentra en la red interna de su organización, seleccione **recuperar configuración automáticamente del almacén de administración central**.</span><span class="sxs-lookup"><span data-stu-id="32a18-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="32a18-107">Si está instalando una réplica del almacén de administración central en un servidor perimetral, puede seleccionar leer la copia exportada del documento de configuración desde un medio portátil, como una unidad flash USB, una unidad de disco duro USB, una unidad de CD-ROM u otros medios.</span><span class="sxs-lookup"><span data-stu-id="32a18-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="32a18-108">Si va a instalar el almacén de configuración local en un servidor perimetral, la información de configuración debe estar en un formato que se haya exportado desde el almacén de administración central ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="32a18-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="32a18-109">Una vez que haya seleccionado la opción adecuada, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32a18-109">After you have selected the appropriate option, click **Next**.</span></span>
  

