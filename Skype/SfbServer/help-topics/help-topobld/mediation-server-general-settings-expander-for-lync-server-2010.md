---
title: Expansor de configuración general del servidor de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Edite las propiedades de los servidores de mediación en este diálogo. En el lado izquierdo hay un conjunto de vínculos rápidos que le lleva a la configuración general, la configuración del próximo salto y la configuración de la puerta de enlace RTC. En cada sección se encuentran los siguientes ajustes:'
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684553"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="06f14-105">Expansor de configuración general del servidor de mediación para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="06f14-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="06f14-106">Edite las propiedades de los servidores de mediación en este diálogo.</span><span class="sxs-lookup"><span data-stu-id="06f14-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="06f14-107">En el lado izquierdo hay un conjunto de vínculos rápidos que le lleva a la configuración general, la configuración del próximo salto y la configuración de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="06f14-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="06f14-108">En cada sección se encuentran los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="06f14-108">In each section are the following settings:</span></span>

 <span data-ttu-id="06f14-109">**General**:</span><span class="sxs-lookup"><span data-stu-id="06f14-109">**General**:</span></span>

- <span data-ttu-id="06f14-110">**FQDN**: usted edita el nombre de dominio completo del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="06f14-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="06f14-111">**Asociaciones**: seleccione la casilla de verificación **asociar grupo perimetral (para componentes multimedia)** y seleccione un servidor perimetral o un grupo perimetral para que el servidor de mediación use como la ruta multimedia para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="06f14-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="06f14-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="06f14-112">**Next hop**:</span></span>

- <span data-ttu-id="06f14-113">**Selección del próximo salto**: seleccione en una lista el servidor front-end o el grupo front-end que se usará como la ruta de acceso del servidor de mediación para la comunicación con su implementación.</span><span class="sxs-lookup"><span data-stu-id="06f14-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="06f14-114">**Puerta de enlace RTC**:</span><span class="sxs-lookup"><span data-stu-id="06f14-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="06f14-115">**Puerta de enlace RTC del servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="06f14-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="06f14-116">**Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="06f14-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="06f14-117">Puede definir un puerto para **TLS** o para la seguridad de la capa de transporte, **TCP**o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="06f14-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="06f14-118">Para que la entrada de puerto para TCP esté disponible, debe activar la casilla de **Habilitar puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="06f14-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="06f14-119">Consulte la documentación y la configuración de la puerta de enlace de la red de telefonía pública conmutada (RTC) para determinar si necesita habilitar y definir los valores de los puertos TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="06f14-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="06f14-120">TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="06f14-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="06f14-121">No todas las puertas de enlace RTC admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="06f14-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="06f14-122">Se muestra una lista de los troncos SIP y las puertas de enlace definidas y configuradas para su implementación.</span><span class="sxs-lookup"><span data-stu-id="06f14-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="06f14-123">Si no hay ninguna entrada presente, no hay ningún troncal o puerta de enlace SIP configurada para su implementación.</span><span class="sxs-lookup"><span data-stu-id="06f14-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="06f14-124">Defina y configure los troncos y las puertas de enlace en **componentes compartidos** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="06f14-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="06f14-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="06f14-125">See also</span></span>

[<span data-ttu-id="06f14-126">Descripción general de la Troncalización SIP</span><span class="sxs-lookup"><span data-stu-id="06f14-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="06f14-127">Opciones de implementación de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="06f14-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
