---
title: Expansor de configuración de servicio de mediación de Front-End de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Para editar las propiedades de la configuración de puerta de enlace de RTC del servidor de mediación en este cuadro de diálogo. Defina las opciones siguientes:'
ms.openlocfilehash: a70ec5e569b60c28e8ec91e86d09ac5f5285ee00
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371494"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="23c8c-104">Expansor de configuración de servicio de mediación de Front-End de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="23c8c-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="23c8c-105">Para editar las propiedades de la configuración de **puerta de enlace RTC del servidor de mediación** en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23c8c-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="23c8c-106">Defina las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="23c8c-106">You define the following settings:</span></span>
  
- <span data-ttu-id="23c8c-107">Seleccione el **servidor de mediación combinado habilitado** si desea instalar el servidor de mediación con este servidor Front-End o Front-End de grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="23c8c-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="23c8c-108">**Puertos de escucha**: definir los puertos de escucha en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="23c8c-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="23c8c-109">Puede definir un puerto para la seguridad de la capa de transporte o de **TLS** o **TCP**, o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="23c8c-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="23c8c-110">Para el puerto de entrada para TCP para que esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="23c8c-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="23c8c-111">Hacer referencia a la configuración de documentación y la configuración de la puerta de enlace de telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="23c8c-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="23c8c-112">TLS es un protocolo más seguro, uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="23c8c-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="23c8c-113">No todas las puertas de enlace de RTC admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="23c8c-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="23c8c-114">Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.</span><span class="sxs-lookup"><span data-stu-id="23c8c-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="23c8c-p105">Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="23c8c-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="23c8c-118">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23c8c-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="23c8c-119">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23c8c-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="23c8c-120">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="23c8c-120">**Help** Displays this help screen.</span></span>
  

