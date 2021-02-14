---
title: Expansor de configuración de equipo perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Para editar las propiedades de un servidor en un grupo de servidores perimetrales, efectúe las acciones siguientes:'
ms.openlocfilehash: a1737303f0c1c6a6f9c9912104b28200eecdc205
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822570"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="8fa59-103">Expansor de configuración de equipo perimetral</span><span class="sxs-lookup"><span data-stu-id="8fa59-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="8fa59-104">Para editar las propiedades de un servidor en un grupo de servidores perimetrales, efectúe las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8fa59-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="8fa59-p101">El valor de **Nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo. El nombre de dominio completo debe coincidir con el registro de host (A) de DNS y el nombre del sujeto del certificado asignado al servidor para la interfaz de red perimetral interna. El valor de **Dirección IP interna** define la dirección IP interna que se asigna a la interfaz de red definida como red interna respecto al diseño de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="8fa59-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="8fa59-108">Las tres secciones siguientes del cuadro de diálogo definen las direcciones IP para la configuración externa de este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8fa59-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="8fa59-109">La opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** en las propiedades del grupo de servidores perimetrales determina la capacidad de cambiar la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="8fa59-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="8fa59-110">Acceso al Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="8fa59-110">SIP Access</span></span>

<span data-ttu-id="8fa59-p103">Edite la dirección IP externa que se asigna a la interfaz de red para acceso al protocolo de inicio de sesión. Esta dirección IP puede ser pública o una de las posibles direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="8fa59-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8fa59-113">Si está habilitada la opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** en la página de configuración del grupo de servidores, solamente se podrá editar la dirección IP para acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="8fa59-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="8fa59-114">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="8fa59-114">Web Conferencing</span></span>

<span data-ttu-id="8fa59-115">Edite la dirección IP externa que se asigna a la interfaz de red para conferencia web.</span><span class="sxs-lookup"><span data-stu-id="8fa59-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="8fa59-116">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="8fa59-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="8fa59-117">Audio o vídeo</span><span class="sxs-lookup"><span data-stu-id="8fa59-117">Audio/Video</span></span>

<span data-ttu-id="8fa59-118">Edite la dirección IP externa que se asigna a la interfaz de red para audio o vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="8fa59-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="8fa59-119">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="8fa59-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="8fa59-p106">El valor de **Dirección IP habilitada para NAT usada** es la dirección pública usada por la interfaz externa para la interfaz de red A/V o el servidor perimetral en general. Si está habilitada la opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**, esta dirección IP se usa para las tres interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="8fa59-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

