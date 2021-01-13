---
title: Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este ejemplo de script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834280"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="cb583-103">Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="cb583-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="cb583-104">El cliente evaluador SIP es un script de PowerShell de ejemplo que puede usar para probar conexiones del controlador de borde de sesión de enrutamiento directo (SBC) en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cb583-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="cb583-105">Este script prueba la funcionalidad básica de un tronco sip (Protocolo de inicio de sesión emparejado por el cliente) con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="cb583-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="cb583-106">El script envía una prueba SIP al ejecutor de pruebas, espera el resultado y, a continuación, lo presenta en un formato legible para la persona.</span><span class="sxs-lookup"><span data-stu-id="cb583-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="cb583-107">Puede usar este script para probar los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="cb583-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="cb583-108">Llamadas salientes y entrantes</span><span class="sxs-lookup"><span data-stu-id="cb583-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="cb583-109">Llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="cb583-109">Simultaneous ring</span></span>
- <span data-ttu-id="cb583-110">Escalación multimedia</span><span class="sxs-lookup"><span data-stu-id="cb583-110">Media escalation</span></span>
- <span data-ttu-id="cb583-111">Transferencia consultiva</span><span class="sxs-lookup"><span data-stu-id="cb583-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="cb583-112">Descargar el script y la documentación</span><span class="sxs-lookup"><span data-stu-id="cb583-112">Download the script and documentation</span></span>

<span data-ttu-id="cb583-113">Descargue la [documentación y el script del cliente del evaluador de SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="cb583-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cb583-114">El script del cliente de evaluador SIP solo adal.ps versión 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="cb583-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="cb583-115">Se devolverá un error si se usa una versión posterior del adal.ps datos.</span><span class="sxs-lookup"><span data-stu-id="cb583-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
