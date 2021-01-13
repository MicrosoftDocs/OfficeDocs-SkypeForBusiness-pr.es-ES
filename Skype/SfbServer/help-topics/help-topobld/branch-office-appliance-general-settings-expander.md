---
title: Expansor de configuración general de aplicación de sucursal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar la configuración de una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, dispone de las secciones siguientes:'
ms.openlocfilehash: 95f842e72066f7ef19c474b10f7293f05c83cd67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833210"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="f7a61-103">Expansor de configuración general de aplicación de sucursal</span><span class="sxs-lookup"><span data-stu-id="f7a61-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="f7a61-104">Para editar la configuración de una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, dispone de las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7a61-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="f7a61-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="f7a61-105">General settings</span></span>

- <span data-ttu-id="f7a61-106">Configuración de resistencia</span><span class="sxs-lookup"><span data-stu-id="f7a61-106">Resiliency settings</span></span>

- <span data-ttu-id="f7a61-107">Configuración del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f7a61-107">Mediation Server settings</span></span>



<span data-ttu-id="f7a61-108">Para una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia, cuenta con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a61-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="f7a61-109">Configuración general</span><span class="sxs-lookup"><span data-stu-id="f7a61-109">General settings</span></span>

<span data-ttu-id="f7a61-p101">El nombre de dominio completo (FQDN) de la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia. Edite el FQDN del servidor para cambiar el valor. Debe tener un registro de host (A) del sistema de nombres de dominio (DNS) que coincida con el valor nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="f7a61-p102">Puede seleccionar **Usar todas las direcciones IP configuradas** o **Limitar el uso de servicio a las direcciones IP seleccionadas**. Si selecciona **Limitar el uso de servicio a las direcciones IP seleccionadas**, definirá la dirección IP principal que utilizará el servidor para todas las comunicaciones excepto para la puerta de enlace de la red de telefonía conmutada (RTC). Defina otra dirección IP para la RTC.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="f7a61-116">En **Asociaciones**, puede editar o especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a61-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="f7a61-117">Asociar servidor de archivado le permite seleccionar asociar un servidor de archivado con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f7a61-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="f7a61-118">Para seleccionar un servidor de archivado que ya está definido, seleccione el  servidor de la lista desplegable o haga clic en Nuevo para especificar un nuevo servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="f7a61-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f7a61-119">Antes de publicar la topología recién definida, el servidor que especifique debe existir y se debe unir en el dominio.</span><span class="sxs-lookup"><span data-stu-id="f7a61-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="f7a61-120">El servidor de supervisión asociado permite asociar un servidor de supervisión con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f7a61-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="f7a61-121">Para seleccionar un servidor de supervisión ya definido, seleccione el servidor de  la lista desplegable o haga clic en Nuevo para especificar un nuevo servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f7a61-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="f7a61-122">Asociar grupo de servidores perimetrales permite asociar un servidor perimetral o un grupo de servidores perimetrales con la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f7a61-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="f7a61-123">Puede seleccionar un servidor perimetral o un grupo de servidores perimetrales que ya estén definidos seleccionándolos en la lista desplegable o hacer clic en **Nuevo** para especificar un servidor perimetral o grupo de servidores perimetrales nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7a61-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="f7a61-124">Resistencia</span><span class="sxs-lookup"><span data-stu-id="f7a61-124">Resiliency</span></span>

<span data-ttu-id="f7a61-p106">La resistencia proporciona una gran disponibilidad al grupo de registradores. Al proporcionar un registrador de copia de seguridad, si el primer registrador falla, el registrador de copia de seguridad puede reemplazar al que ha fallado de modo que los usuarios puedan seguir registrándose y comunicándose. Es posible que algunos usuarios tengan una funcionalidad reducida según los sistemas que hayan fallado con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="f7a61-128">En la lista desplegable, seleccione el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition que actuará como registrador de reserva para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f7a61-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="f7a61-129">También puede habilitar intervalos de tiempo de la conmutación por error y conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="f7a61-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="f7a61-130">Al habilitar la configuración de tiempo de la conmutación por error y la conmutación por recuperación (especificada en segundos) se habilita la detección automática de los registradores erróneos, y el tiempo de conmutación por recuperación que permite la determinación automática que el principal vuelve a estar recuperado y puede retomar el proceso del registrador.</span><span class="sxs-lookup"><span data-stu-id="f7a61-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7a61-131">Al definir la detección de fallos y el intervalo de conmutación por recuperación, tenga mucho cuidado de no introducir un intervalo que provoque la ejecución de la conmutación por error y por recuperación en el caso que el registrador no logre responder durante un espacio breve de tiempo.</span><span class="sxs-lookup"><span data-stu-id="f7a61-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="f7a61-132">Es posible que el registrador principal no responda durante breves periodos de tiempo en función de la carga de los grupos o servidores.</span><span class="sxs-lookup"><span data-stu-id="f7a61-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="f7a61-133">Los valores predeterminados para una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en un sitio a un grupo o servidor front-end Standard Edition son 120 segundos para la conmutación por error y 240 segundos para la reserva.</span><span class="sxs-lookup"><span data-stu-id="f7a61-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="f7a61-134">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f7a61-134">Mediation Server</span></span>

<span data-ttu-id="f7a61-135">Para **Servidor de mediación** puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a61-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="f7a61-136">La casilla de verificación **Servidor de mediación combinado habilitado** no está disponible en una Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia porque el servidor de mediación está combinado.</span><span class="sxs-lookup"><span data-stu-id="f7a61-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="f7a61-p109">Defina el puerto de escucha de los servidores del grupo para la Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación combinado. Esta configuración es opcional y debería consultar los requisitos de su puerta de enlace o de la RTC para determinar si la necesita. De forma predeterminada, el valor del puerto TCP es 5068.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="f7a61-p110">Defina las puertas de enlace de la RTC que están asociadas con el servidor de mediación combinado. Si ya ha definido puertas de enlace, éstas se podrán asociar con el servidor de mediación. Si no a definido ninguna puerta de enlace, pero las tiene disponibles para definirlas, puede seleccionar **Nuevo**. También puede quitar puertas de enlace que ya estén configuradas para este servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="f7a61-p111">Si tiene más de una puerta de enlace asociada con el servidor de mediación, la primera puerta de enlace asociada será la predeterminada. Si debe elegir otra puerta de enlace como predeterminada, seleccione la que desee y, a continuación, haga clic en **Convertir en predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="f7a61-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7a61-149">Ver también</span><span class="sxs-lookup"><span data-stu-id="f7a61-149">See also</span></span>

<span data-ttu-id="f7a61-150">Para más información sobre cómo definir y configurar la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia, consulte [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7a61-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


