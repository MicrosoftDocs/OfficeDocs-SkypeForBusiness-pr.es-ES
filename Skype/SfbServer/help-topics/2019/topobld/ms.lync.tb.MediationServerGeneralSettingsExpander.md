---
title: Expansor de configuración general del servidor de mediación
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 27a93cb0894f7791b689e4b8fcc3246ab6d9415d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979752"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="203d5-102">Expansor de configuración general del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="203d5-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="203d5-103">Configuración general</span><span class="sxs-lookup"><span data-stu-id="203d5-103">General settings</span></span>

<span data-ttu-id="203d5-104">Nombre de dominio completo (FQDN) del grupo de servidores de mediación o del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="203d5-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="203d5-105">Edite el FQDN del servidor para cambiar el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="203d5-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="203d5-106">Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="203d5-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="203d5-107">En la sección **asociaciones** , seleccione un servidor perimetral o grupo de servidores perimetrales para asociar con el grupo de servidores de mediación o el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="203d5-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="203d5-108">Seleccione el borde que se va a usar componentes de medios del servidor de mediación para usuarios externos de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="203d5-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="203d5-109">Si no tiene un servidor perimetral actualmente definidos y necesita para asociar el servidor de mediación a un servidor perimetral, haga clic en **nuevo** y defina el nuevo servidor perimetral o grupo de servidores perimetrales en la definir el Asistente de grupo de servidores perimetrales nuevo.</span><span class="sxs-lookup"><span data-stu-id="203d5-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="203d5-110">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="203d5-110">Next hop settings</span></span>

<span data-ttu-id="203d5-111">Especificar el grupo de servidores de mediación o próximo salto del servidor de mediación seleccionando el grupo definido de Front-End de Enterprise Edition o Standard Edition front-end de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="203d5-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="203d5-112">Un Director o el Director de grupo de servidores no es una selección válida para un grupo de servidores de mediación o el próximo salto del servidor de mediación y no aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="203d5-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="203d5-113">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="203d5-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="203d5-114">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="203d5-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="203d5-115">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="203d5-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="203d5-116">Definir las puertas de enlace de RTC que están asociados con el grupo de servidores de mediación o el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="203d5-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="203d5-117">Si ya se han definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="203d5-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="203d5-118">Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor en los servidores del grupo para la Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="203d5-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="203d5-119">Este puerto es 5067 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="203d5-119">By default, this port is 5067.</span></span> <span data-ttu-id="203d5-120">Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado.</span><span class="sxs-lookup"><span data-stu-id="203d5-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="203d5-121">Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto.</span><span class="sxs-lookup"><span data-stu-id="203d5-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="203d5-122">El valor de este puerto es 5068 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="203d5-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="203d5-p105">Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="203d5-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="203d5-125">Si tiene más de un tronco asociado con un servidor de mediación, puede especificar un tronco predeterminada seleccionando el tronco y, a continuación, haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="203d5-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="203d5-126">Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="203d5-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

