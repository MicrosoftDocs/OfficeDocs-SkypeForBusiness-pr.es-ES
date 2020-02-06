---
title: Expansor de configuración de equipo perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar las propiedades de un servidor de un grupo de servidores perimetrales, haga lo siguiente:'
ms.openlocfilehash: 1b2fce33b65e744c8ba2f18107d4f6bc5369b8de
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793808"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="93e04-103">Expansor de configuración de equipo perimetral</span><span class="sxs-lookup"><span data-stu-id="93e04-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="93e04-104">Para editar las propiedades de un servidor de un grupo de servidores perimetrales, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93e04-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="93e04-105">El **nombre interno o FQDN** se puede cambiar editando el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="93e04-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="93e04-106">El FQDN debe coincidir con el registro del host (A) del sistema de nombres de dominio (DNS) y el nombre de asunto del certificado asignado al servidor para la interfaz de red perimetral interna.</span><span class="sxs-lookup"><span data-stu-id="93e04-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="93e04-107">El valor de **dirección IP interna** define la dirección IP que se asigna a la interfaz de red que se define como una red interna, en relación con el diseño de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="93e04-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="93e04-108">Las tres secciones siguientes del cuadro de diálogo definen las direcciones IP de la configuración externa de este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="93e04-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="93e04-109">La posibilidad de cambiar las direcciones IP se ve afectada por el parámetro habilitar las opciones **de FQDN e IP separadas para conferencias web y a/V** en la configuración de propiedades en el nivel de grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="93e04-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="93e04-110">Acceso SIP</span><span class="sxs-lookup"><span data-stu-id="93e04-110">SIP Access</span></span>

<span data-ttu-id="93e04-111">Edite la dirección IP externa asignada a la interfaz de red para el acceso por protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="93e04-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="93e04-112">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="93e04-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93e04-113">Si la opción **Habilitar FQDN y la dirección IP para las conferencias web y a/V** en la página Configuración del grupo está habilitada, solo la dirección IP del acceso SIP estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="93e04-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="93e04-114">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="93e04-114">Web Conferencing</span></span>

<span data-ttu-id="93e04-115">Edite la dirección IP externa asignada a la interfaz de red para las conferencias web.</span><span class="sxs-lookup"><span data-stu-id="93e04-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="93e04-116">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="93e04-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="93e04-117">Audio o vídeo</span><span class="sxs-lookup"><span data-stu-id="93e04-117">Audio/Video</span></span>

<span data-ttu-id="93e04-118">Edite la dirección IP externa asignada a la interfaz de red para audio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="93e04-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="93e04-119">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="93e04-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="93e04-120">La configuración de la **dirección IP pública habilitada para NAT usada** es la dirección pública que usa la interfaz externa para la interfaz de red a/V o el servidor perimetral en general.</span><span class="sxs-lookup"><span data-stu-id="93e04-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="93e04-121">Si el valor **Habilitar FQDN e IP diferentes para conferencias web y a/V** está habilitado, esta dirección IP pública se usa para las tres interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="93e04-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

