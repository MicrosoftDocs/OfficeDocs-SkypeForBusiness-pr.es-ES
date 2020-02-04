---
title: Expansor de configuración del servicio de mediación front-end para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite las propiedades de la configuración de la puerta de enlace RTC del servidor de mediación en este diálogo. Defina la siguiente configuración:'
ms.openlocfilehash: bd24c24d14e24ed7e4ce53bc30d01b2e955be6cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697285"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ea33c-104">Expansor de configuración del servicio de mediación front-end para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ea33c-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ea33c-105">Edite las propiedades de la configuración de la **puerta de enlace RTC del servidor de mediación** en este diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea33c-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="ea33c-106">Defina la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ea33c-106">You define the following settings:</span></span>
  
- <span data-ttu-id="ea33c-107">Seleccione el **servidor de mediación agrupado habilitado** si desea Collocate el servidor de mediación con este servidor front-end o grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="ea33c-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="ea33c-108">**Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ea33c-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="ea33c-109">Puede definir un puerto para **TLS** o para la seguridad de la capa de transporte, **TCP**o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="ea33c-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="ea33c-110">Para que la entrada de puerto para TCP esté disponible, debe activar la casilla de **Habilitar puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="ea33c-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ea33c-111">Consulte la documentación y la configuración de la puerta de enlace de la red de telefonía pública conmutada (RTC) para determinar si necesita habilitar y definir los valores de los puertos TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="ea33c-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="ea33c-112">TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea33c-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ea33c-113">No todas las puertas de enlace RTC admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="ea33c-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="ea33c-114">Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.</span><span class="sxs-lookup"><span data-stu-id="ea33c-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="ea33c-p105">Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ea33c-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="ea33c-118">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea33c-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="ea33c-119">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea33c-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="ea33c-120">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="ea33c-120">**Help** Displays this help screen.</span></span>
  

