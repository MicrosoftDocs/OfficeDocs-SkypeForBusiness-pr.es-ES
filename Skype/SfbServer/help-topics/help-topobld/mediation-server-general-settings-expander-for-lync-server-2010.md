---
title: Expansor de configuración general del servidor de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Las propiedades de los servidores de mediación se editan en este cuadro de diálogo. En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC. En cada sección se encuentran las siguientes opciones:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806750"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="62555-105">Expansor de configuración general del servidor de mediación para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="62555-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="62555-106">Las propiedades de los servidores de mediación se editan en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="62555-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="62555-107">En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="62555-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="62555-108">En cada sección se encuentran las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="62555-108">In each section are the following settings:</span></span>

 <span data-ttu-id="62555-109">**General:**</span><span class="sxs-lookup"><span data-stu-id="62555-109">**General**:</span></span>

- <span data-ttu-id="62555-110">**FQDN:** edite el nombre de dominio completo del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="62555-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="62555-111">**Asociaciones:** active la casilla Asociar grupo de servidores perimetrales (para componentes **multimedia)** y seleccione un servidor perimetral o un grupo de servidores perimetrales para que el servidor de mediación lo use como ruta de acceso multimedia para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="62555-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="62555-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="62555-112">**Next hop**:</span></span>

- <span data-ttu-id="62555-113">**Selección del próximo salto:** seleccione en una lista el servidor front-end o el grupo de servidores front-end que se usará como ruta de acceso para el servidor de mediación que se usará para comunicarse con la implementación.</span><span class="sxs-lookup"><span data-stu-id="62555-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="62555-114">**Puerta de enlace RTC**:</span><span class="sxs-lookup"><span data-stu-id="62555-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="62555-115">**Puerta de enlace RTC del servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="62555-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="62555-116">**Puertos de escucha:** defina los puertos en los que escuchará el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="62555-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="62555-117">Puede definir un puerto para **TLS** o seguridad de la capa de transporte, o **TCP**, o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="62555-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="62555-118">Para que la entrada de puerto de TCP esté disponible, debe seleccionar la casilla de verificación **Habilitar puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="62555-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="62555-119">Consulte la documentación y los ajustes de configuración de la puerta de enlace de la red telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="62555-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="62555-120">TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="62555-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="62555-121">No todas las puertas de enlace RTC son compatibles con TLS.</span><span class="sxs-lookup"><span data-stu-id="62555-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="62555-122">Se muestra una lista de los troncos SIP y las puertas de enlace que se han definido y configurado para la implementación.</span><span class="sxs-lookup"><span data-stu-id="62555-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="62555-123">Si no se muestra ninguna entrada, significa que no hay troncos SIP ni puertas de enlace RTC configurados para la implementación.</span><span class="sxs-lookup"><span data-stu-id="62555-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="62555-124">Puede definir y configurar troncos y puertas de enlace en **Componentes compartidos** en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="62555-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="62555-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="62555-125">See also</span></span>

[<span data-ttu-id="62555-126">Información general sobre los enlaces troncales SIP</span><span class="sxs-lookup"><span data-stu-id="62555-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="62555-127">Opciones de implementación de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="62555-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
