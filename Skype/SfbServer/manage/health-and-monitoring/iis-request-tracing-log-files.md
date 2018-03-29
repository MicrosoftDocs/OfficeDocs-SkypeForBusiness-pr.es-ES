---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Conozca el servicio de movilidad (Mcx) en Skype para 2015 de Business Server compatibilidad con clientes heredados.'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="a1970-103">Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1970-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a1970-104">**Resumen:** Obtenga información acerca del servicio de movilidad (Mcx) en Skype para 2015 de Business Server compatibilidad con clientes heredados.</span><span class="sxs-lookup"><span data-stu-id="a1970-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="a1970-105">Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).</span><span class="sxs-lookup"><span data-stu-id="a1970-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>
  
<span data-ttu-id="a1970-106">Al habilitar el seguimiento de la solicitud de servicios de Internet Information Server (IIS) para el Skype para servicio de movilidad Business Server (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día.</span><span class="sxs-lookup"><span data-stu-id="a1970-106">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="a1970-107">El registro de seguimiento de IIS está habilitado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a1970-107">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="a1970-108">Debe supervisar los servidores frontales para asegurarse de que no se ejecutan fuera del espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="a1970-108">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="a1970-109">De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="a1970-109">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="a1970-110">Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1970-110">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="a1970-111">Para obtener más información acerca del comando **httpLogging** , consulte [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="a1970-111">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

