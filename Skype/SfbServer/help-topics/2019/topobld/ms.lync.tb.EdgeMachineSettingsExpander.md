---
title: Expansor de configuración de equipo perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor en un grupo de servidores perimetrales, haga lo siguiente:'
ms.openlocfilehash: 3570675fd82512aa25d760c2380f05a2de80cec6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990199"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="b5cd4-103">Expansor de configuración de equipo perimetral</span><span class="sxs-lookup"><span data-stu-id="b5cd4-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="b5cd4-104">Para editar las propiedades de un servidor en un grupo de servidores perimetrales, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5cd4-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="b5cd4-105">El **nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b5cd4-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b5cd4-106">El FQDN debe coincidir con el registro (A) de host del sistema de nombres de dominio (DNS) y el nombre de sujeto del certificado asignado al servidor para la interfaz de red perimetral interna.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="b5cd4-107">El valor de la **dirección IP interna** define la dirección IP que se asigna a la interfaz de red que se ha definido como una red interna, en relación con el diseño de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="b5cd4-108">Las tres secciones del cuadro de diálogo Definición las direcciones IP para la configuración de este servidor perimetral externa.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="b5cd4-109">La capacidad para cambiar las direcciones IP se ve afectada por el valor de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** en la configuración de las propiedades en el servidor perimetral de nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="b5cd4-110">Acceso SIP</span><span class="sxs-lookup"><span data-stu-id="b5cd4-110">SIP Access</span></span>

<span data-ttu-id="b5cd4-111">Editar la dirección IP externa que se asigna a la interfaz de red para el acceso de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="b5cd4-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="b5cd4-112">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5cd4-113">Si la configuración de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** en el grupo de página de configuración está habilitada, sólo la dirección IP para el acceso de SIP estará disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="b5cd4-114">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="b5cd4-114">Web Conferencing</span></span>

<span data-ttu-id="b5cd4-115">Editar la dirección IP externa que se asigna a la interfaz de red para las conferencias web.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="b5cd4-116">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="b5cd4-117">Audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="b5cd4-117">Audio/Video</span></span>

<span data-ttu-id="b5cd4-118">Editar la dirección IP externa que se asigna a la interfaz de red para audio y vídeo (A / V).</span><span class="sxs-lookup"><span data-stu-id="b5cd4-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="b5cd4-119">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="b5cd4-120">El valor de la **dirección IP pública usado habilitado para NAT** es la dirección pública que usa la interfaz externa para puede ser el V red interfaz o el servidor perimetral en general.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="b5cd4-121">Si la configuración de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** está habilitada, esta dirección IP pública se utiliza para todas las tres interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="b5cd4-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

