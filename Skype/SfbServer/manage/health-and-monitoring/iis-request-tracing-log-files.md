---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Obtenga información sobre el servicio de movilidad (Mcx) en Skype para soporte técnico de Business Server 2015 para los clientes heredados.'
ms.openlocfilehash: 6c885c441531dc02e149ee1fb37f0001d252811f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873467"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="1c41d-103">Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c41d-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1c41d-104">**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) en Skype para soporte técnico de Business Server 2015 para los clientes heredados.</span><span class="sxs-lookup"><span data-stu-id="1c41d-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="1c41d-105">Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).</span><span class="sxs-lookup"><span data-stu-id="1c41d-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="1c41d-106">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1c41d-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="1c41d-107">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="1c41d-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="1c41d-108">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="1c41d-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="1c41d-109">Cuando se habilita el seguimiento de solicitudes de Internet Information Services (IIS) para el Skype para servicio de movilidad de servidor empresarial (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día.</span><span class="sxs-lookup"><span data-stu-id="1c41d-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="1c41d-110">El registro de seguimiento de IIS está habilitado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c41d-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="1c41d-111">Debe supervisar los servidores Front-End para asegurarse de que no se ejecutan fuera del espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="1c41d-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="1c41d-112">De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="1c41d-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="1c41d-113">Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c41d-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="1c41d-114">Para obtener información detallada sobre el comando **httpLogging** , vea [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="1c41d-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

