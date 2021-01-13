---
title: Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: obtenga información sobre el servicio de movilidad (Mcx) en la compatibilidad de Skype Empresarial Server 2015 para clientes heredados.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823510"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="e5cf8-103">Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5cf8-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e5cf8-104">**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) en la compatibilidad de Skype Empresarial Server 2015 para clientes heredados.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="e5cf8-105">Este tema se aplica solo a las implementaciones que admiten clientes de Lync 2010 Lync Mobile y está destinado al servicio de movilidad (Mcx).</span><span class="sxs-lookup"><span data-stu-id="e5cf8-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="e5cf8-106">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5cf8-107">Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e5cf8-108">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="e5cf8-109">Cuando habilita el seguimiento de solicitudes de Internet Information Services (IIS) para el servicio de movilidad de Skype Empresarial Server (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="e5cf8-110">El registro de seguimiento de IIS está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="e5cf8-111">Debe supervisar los servidores front-end para asegurarse de que no se quedas sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="e5cf8-112">De forma predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="e5cf8-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="e5cf8-113">Para desactivar el seguimiento de solicitudes IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5cf8-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="e5cf8-114">Para obtener más información sobre **el comando httpLogging,** vea [la referencia del comando.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="e5cf8-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

