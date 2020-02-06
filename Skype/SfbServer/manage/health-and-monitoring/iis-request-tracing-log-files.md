---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Obtenga información sobre el servicio de movilidad (MCX) en la compatibilidad de Skype empresarial Server 2015 para clientes heredados.'
ms.openlocfilehash: 982e5842499e5cb2f6ff21ff884d1baa45075627
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817930"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="2d721-103">Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d721-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d721-104">**Resumen:** Obtenga más información sobre el servicio de movilidad (MCX) en la compatibilidad de Skype empresarial Server 2015 para clientes heredados.</span><span class="sxs-lookup"><span data-stu-id="2d721-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="2d721-105">Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).</span><span class="sxs-lookup"><span data-stu-id="2d721-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="2d721-106">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2d721-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2d721-107">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="2d721-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2d721-108">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="2d721-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="2d721-109">Al habilitar el seguimiento de solicitudes de servicios de Internet Information Server (IIS) para el servicio de movilidad de Skype empresarial (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en el disco por día.</span><span class="sxs-lookup"><span data-stu-id="2d721-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="2d721-110">El registro de seguimiento de IIS está habilitado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d721-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="2d721-111">Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="2d721-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="2d721-112">De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="2d721-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="2d721-113">Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d721-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="2d721-114">Para obtener más información sobre el comando **httpLogging** , vea [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="2d721-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

