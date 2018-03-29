---
title: Ampliador de configuración de máquina borde
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor en un grupo de servidores de borde, haga lo siguiente:'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="47ab9-103">Ampliador de configuración de máquina borde</span><span class="sxs-lookup"><span data-stu-id="47ab9-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="47ab9-104">Para editar las propiedades de un servidor en un grupo de servidores de borde, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47ab9-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="47ab9-105">El **nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="47ab9-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="47ab9-106">El FQDN debe coincidir con el registro (A) de host de sistema de nombres de dominio (DNS) y el nombre del sujeto del certificado asignado al servidor de la interfaz de red interna de borde.</span><span class="sxs-lookup"><span data-stu-id="47ab9-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="47ab9-107">El valor de la **dirección IP interna** define la dirección IP que se asigna a la interfaz de red se define como una red interna, en relación con el diseño de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="47ab9-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="47ab9-108">Las tres secciones del cuadro de diálogo definen las direcciones IP de la configuración de este servidor perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="47ab9-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="47ab9-109">La capacidad de cambiar las direcciones IP se ve afectada por el valor de **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** en la configuración de propiedades en el servidor perimetral de nivel de la piscina.</span><span class="sxs-lookup"><span data-stu-id="47ab9-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="47ab9-110">Acceso SIP</span><span class="sxs-lookup"><span data-stu-id="47ab9-110">SIP Access</span></span>

<span data-ttu-id="47ab9-111">Editar la dirección IP externa que se asigna a la interfaz de red para el acceso de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="47ab9-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="47ab9-112">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="47ab9-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47ab9-113">Si el valor de **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** en el fondo de página configuración está habilitada, sólo estará disponible para editar la dirección IP para acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="47ab9-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="47ab9-114">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="47ab9-114">Web Conferencing</span></span>

<span data-ttu-id="47ab9-115">Editar la dirección IP externa que se asigna a la interfaz de red para conferencias web.</span><span class="sxs-lookup"><span data-stu-id="47ab9-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="47ab9-116">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="47ab9-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="47ab9-117">Audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="47ab9-117">Audio/Video</span></span>

<span data-ttu-id="47ab9-118">Editar la dirección IP externa que se asigna a la interfaz de red de audio y vídeo (A / V).</span><span class="sxs-lookup"><span data-stu-id="47ab9-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="47ab9-119">Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.</span><span class="sxs-lookup"><span data-stu-id="47ab9-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="47ab9-120">La configuración de **NAT compatible con dirección IP pública que se utiliza** es la dirección pública utilizada por la interfaz externa en lugar de A cualquiera / V red interfaz o el servidor perimetral en general.</span><span class="sxs-lookup"><span data-stu-id="47ab9-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="47ab9-121">Si la configuración **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** está habilitada, esta dirección IP pública se utiliza para las tres interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="47ab9-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

