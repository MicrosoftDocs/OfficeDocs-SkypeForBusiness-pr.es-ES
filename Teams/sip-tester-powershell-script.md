---
title: Script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este ejemplo de script de PowerShell para probar el enrutamiento directo de las conexiones de controlador de borde de sesión en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951265"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="2bc1e-103">Script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión</span><span class="sxs-lookup"><span data-stu-id="2bc1e-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="2bc1e-104">El cliente SIP Tester es un script de PowerShell de ejemplo que puede usar para probar el enrutamiento directo de las conexiones de controlador de borde de sesión (SBC) en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="2bc1e-105">Este script prueba la funcionalidad básica de un tronco de protocolo de inicio de sesión (SIP) emparejado por el cliente con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="2bc1e-106">El script envía una prueba SIP al Ejecutor de pruebas, espera el resultado y, a continuación, lo presenta en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="2bc1e-107">Puede usar este script para probar los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bc1e-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="2bc1e-108">Llamadas salientes y entrantes</span><span class="sxs-lookup"><span data-stu-id="2bc1e-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="2bc1e-109">Llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="2bc1e-109">Simultaneous ring</span></span>
- <span data-ttu-id="2bc1e-110">Escalado de elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="2bc1e-110">Media escalation</span></span>
- <span data-ttu-id="2bc1e-111">Transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="2bc1e-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="2bc1e-112">Descargar la secuencia de comandos y la documentación</span><span class="sxs-lookup"><span data-stu-id="2bc1e-112">Download the script and documentation</span></span>

<span data-ttu-id="2bc1e-113">Descargue el [script y la documentación del cliente de prueba SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="2bc1e-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="2bc1e-114">El script de cliente del evaluador SIP solo admite adal.ps versión 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="2bc1e-115">Se devolverá un error si se usa una versión posterior de adal.ps.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
