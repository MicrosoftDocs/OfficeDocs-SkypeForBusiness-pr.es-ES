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
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite las propiedades de la configuración de la Puerta de enlace RTC del servidor de mediación en este cuadro de diálogo. Defina la configuración siguiente:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217731"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d95f1-104">Expansor de configuración del servicio de mediación front-end para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d95f1-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d95f1-105">Edite las propiedades de la configuración de la **Puerta de enlace RTC del servidor de mediación** en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d95f1-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="d95f1-106">Defina la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="d95f1-106">You define the following settings:</span></span>
  
- <span data-ttu-id="d95f1-107">Seleccione el **servidor de mediación combinado habilitado** si desea combinar el servidor de mediación con este servidor front-end o grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d95f1-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="d95f1-108">**Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d95f1-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="d95f1-109">Puede definir un puerto para **TLS** o seguridad de la capa de transporte, o **TCP**, o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="d95f1-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="d95f1-110">Para que la entrada de puerto de TCP esté disponible, debe seleccionar la casilla de verificación **Habilitar puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="d95f1-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d95f1-111">Consulte la documentación y los ajustes de configuración de la puerta de enlace de la red telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="d95f1-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="d95f1-112">TLS es un protocolo más seguro, con certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="d95f1-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="d95f1-113">No todas las puertas de enlace de RTC admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="d95f1-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="d95f1-114">Una lista del **Tronco** (es decir, troncos de protocolo de inicio de sesión (SIP)), **Puerta de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.</span><span class="sxs-lookup"><span data-stu-id="d95f1-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="d95f1-p105">Seleccione un Tronco, una Puerta de enlace y un Sitio y haga clic en **Convertir en predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **Eliminar predeterminado** para eliminar la selección de los valores predeterminados. A continuación debe seleccionar un nuevo valor predeterminado y hacer clic en **Convertir en predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="d95f1-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="d95f1-118">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d95f1-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d95f1-119">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d95f1-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d95f1-120">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="d95f1-120">**Help** Displays this help screen.</span></span>
  

