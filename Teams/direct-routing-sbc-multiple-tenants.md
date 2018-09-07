---
title: Configurar un controlador de borde de sesión para varios inquilinos
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Obtenga información sobre cómo configurar un controlador de borde de sesión (SBC) para servir a varios inquilinos.
ms.openlocfilehash: 3073800a6c200bcaeffafb557d6ea149dee598cd
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866462"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="e06ef-103">Configurar un controlador de borde de sesión para varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="e06ef-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="e06ef-104">Enrutamiento directo admite configurar una sesión de controlador de borde (SBC) para servir a varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e06ef-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="e06ef-105">Este escenario está diseñada para los socios de Microsoft o los operadores de RTC, denominados operadores más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="e06ef-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="e06ef-106">Una compañía vende entregados a Microsoft Teams a sus clientes de servicios de telefonía.</span><span class="sxs-lookup"><span data-stu-id="e06ef-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="e06ef-107">Un operador:</span><span class="sxs-lookup"><span data-stu-id="e06ef-107">A carrier:</span></span>
- <span data-ttu-id="e06ef-108">Implemente y administre un SBC en su centro de datos (no es necesario implementar un SBC los clientes, y que reciben los servicios de telefonía de la compañía en el cliente de los equipos).</span><span class="sxs-lookup"><span data-stu-id="e06ef-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="e06ef-109">Interconexiones la SBC para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e06ef-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="e06ef-110">Proporciona servicios de RTC a los clientes.</span><span class="sxs-lookup"><span data-stu-id="e06ef-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="e06ef-111">Administra la calidad de las llamadas de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="e06ef-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="e06ef-112">Cargos por separado para los servicios de RTC.</span><span class="sxs-lookup"><span data-stu-id="e06ef-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="e06ef-113">Microsoft no administra los operadores.</span><span class="sxs-lookup"><span data-stu-id="e06ef-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="e06ef-114">Microsoft ofrece un sistema PBX (sistema de teléfono de Microsoft) y un cliente de los equipos, certifica teléfonos y certifica SBCs que se pueden usar con el sistema de teléfono de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e06ef-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="e06ef-115">Antes de elegir un operador, por favor, asegúrese de que su elección tiene un SBC certificado y puede administrar la calidad de voz de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="e06ef-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="e06ef-116">Los siguientes son los pasos de implementación técnica para configurar el escenario.</span><span class="sxs-lookup"><span data-stu-id="e06ef-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="e06ef-117">**Sólo del proveedor:**</span><span class="sxs-lookup"><span data-stu-id="e06ef-117">**Carrier only:**</span></span>
1. <span data-ttu-id="e06ef-118">Implementar la SBC y configurarlo para el escenario de hospedaje según las [instrucciones de los proveedores SBC certificadas](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="e06ef-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="e06ef-119">Registrar un nombre de dominio base en el inquilino de portadora y solicitar un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="e06ef-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="e06ef-120">Registrar un subdominio para cada cliente, que forma parte del dominio base.</span><span class="sxs-lookup"><span data-stu-id="e06ef-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="e06ef-121">**Operador con un administrador Global de cliente:**</span><span class="sxs-lookup"><span data-stu-id="e06ef-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="e06ef-122">Agregue el nombre de subdominio para el inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="e06ef-123">Activar el nombre de subdominio.</span><span class="sxs-lookup"><span data-stu-id="e06ef-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="e06ef-124">Configure el tronco en la compañía a los usuarios de inquilinos y aprovisionamiento de cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="e06ef-125">*Por favor, asegúrese de que comprende los conceptos básicos DNS y cómo se administra el nombre de dominio en Office 365. [Obtener ayuda con Office 365 dominios](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) se revise antes de continuar.*</span><span class="sxs-lookup"><span data-stu-id="e06ef-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="e06ef-126">Implementar y configurar el SBC</span><span class="sxs-lookup"><span data-stu-id="e06ef-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="e06ef-127">Para obtener instrucciones detalladas acerca de cómo implementar y configurar SBCs para un escenario de hospedaje de SBC, hacer referencia a la documentación del proveedor SBC.</span><span class="sxs-lookup"><span data-stu-id="e06ef-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="e06ef-128">**AudioCodes:** [Notas de configuración de enrutamiento directo](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuración de la SBC que hospeda el escenario descrito en "Connecting AudioCodes SBC a Microsoft Teams directa enrutamiento Hosting modelo configuración Nota".</span><span class="sxs-lookup"><span data-stu-id="e06ef-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="e06ef-129">**La cinta de opciones Communications:** Para escenarios de hospedaje de SBC, se admite solo la serie de núcleo.</span><span class="sxs-lookup"><span data-stu-id="e06ef-129">**Ribbon Communications:** For SBC hosting scenarios, only the core series is supported.</span></span> <span data-ttu-id="e06ef-130">Consulte la [Guía de configuración de los equipos de Microsoft de la cinta de opciones Communications SBC principales](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span><span class="sxs-lookup"><span data-stu-id="e06ef-130">Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span></span>

> [!NOTE]
> <span data-ttu-id="e06ef-131">Por favor, preste atención a cómo configurar el encabezado "Contacto".</span><span class="sxs-lookup"><span data-stu-id="e06ef-131">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="e06ef-132">El encabezado de contacto se usa para buscar al inquilino del cliente en el mensaje de invitación entrante.</span><span class="sxs-lookup"><span data-stu-id="e06ef-132">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="e06ef-133">Registrar un dominio base y subdominios</span><span class="sxs-lookup"><span data-stu-id="e06ef-133">Register a base domain and subdomains</span></span>

<span data-ttu-id="e06ef-134">Para el escenario de hospedaje, debe crear:</span><span class="sxs-lookup"><span data-stu-id="e06ef-134">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="e06ef-135">Un nombre de dominio base que pertenecen a la compañía.</span><span class="sxs-lookup"><span data-stu-id="e06ef-135">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="e06ef-136">Un subdominio que forma parte del nombre de dominio base en cada inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-136">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="e06ef-137">En el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e06ef-137">In the following example:</span></span>
- <span data-ttu-id="e06ef-138">Adatum es un operador que sirve de varios clientes proporcionando servicios de Internet y telefonía.</span><span class="sxs-lookup"><span data-stu-id="e06ef-138">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="e06ef-139">Woodgrove Bank, Contoso y Adventure Works son tres los clientes que tienen dominios de Office 365 pero que reciben los servicios de telefonía de Adatum.</span><span class="sxs-lookup"><span data-stu-id="e06ef-139">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="e06ef-140">Subdominios **debe** coincidir con el nombre FQDN del tronco que se configuran para el cliente y el FQDN en el encabezado de contacto al enviar la invitación a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e06ef-140">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="e06ef-141">Cuando una llamada llega a la interfaz de enrutamiento directo de Office 365, la interfaz utiliza el encabezado de contacto para buscar al inquilino donde el usuario debe ser consultado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-141">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="e06ef-142">Enrutamiento directas no usar búsqueda de número de teléfono en la invitación, que algunos clientes podrían tener que no sean-números que pueden se superponen en varios inquilinos DID.</span><span class="sxs-lookup"><span data-stu-id="e06ef-142">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="e06ef-143">Por lo tanto, es necesario el nombre FQDN en el encabezado de contacto para identificar el inquilino exacto para buscar el usuario por el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e06ef-143">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="e06ef-144">*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre la creación de nombres de dominio en los inquilinos de Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e06ef-144">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="e06ef-145">El diagrama siguiente resume los requisitos de dominio base, subdominios y encabezado de contacto.</span><span class="sxs-lookup"><span data-stu-id="e06ef-145">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Requisitos de dominio base, subdominios y encabezado de contacto](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="e06ef-147">La SBC requiere un certificado para autenticar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="e06ef-147">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="e06ef-148">Para el escenario de hospedaje de SBC, el operador debe solicitar un certificado con SAN \* \*.base_domain (por ejemplo, \*customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="e06ef-148">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="e06ef-149">Este certificado puede usarse para autenticar las conexiones a varios inquilinos procesadas por un SBC único.</span><span class="sxs-lookup"><span data-stu-id="e06ef-149">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="e06ef-150">La tabla siguiente es un ejemplo de una configuración.</span><span class="sxs-lookup"><span data-stu-id="e06ef-150">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="e06ef-151">Nuevo nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-151">New domain name</span></span> |<span data-ttu-id="e06ef-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="e06ef-152">Type</span></span>|<span data-ttu-id="e06ef-153">Registrado</span><span class="sxs-lookup"><span data-stu-id="e06ef-153">Registered</span></span>  |<span data-ttu-id="e06ef-154">Certificado SAN de SBC</span><span class="sxs-lookup"><span data-stu-id="e06ef-154">Certificate SAN for SBC</span></span>  |<span data-ttu-id="e06ef-155">Dominio de inquilinos predeterminado en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e06ef-155">Tenant default domain in the example</span></span>  |<span data-ttu-id="e06ef-156">Nombre del FQDN que debe presentar SBC en el encabezado de contacto al enviar las llamadas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="e06ef-156">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="e06ef-157">Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-157">customers.adatum.biz</span></span>|    <span data-ttu-id="e06ef-158">Base</span><span class="sxs-lookup"><span data-stu-id="e06ef-158">Base</span></span>     |     <span data-ttu-id="e06ef-159">En el inquilino de operador</span><span class="sxs-lookup"><span data-stu-id="e06ef-159">In carrier tenant</span></span>  |    <span data-ttu-id="e06ef-160">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-160">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="e06ef-161">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-161">adatum.biz</span></span>      |<span data-ttu-id="e06ef-162">NA, este es un inquilino de servicio, ningún usuario</span><span class="sxs-lookup"><span data-stu-id="e06ef-162">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="e06ef-163">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-163">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="e06ef-164">Subdominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-164">Subdomain</span></span>  |    <span data-ttu-id="e06ef-165">En un inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="e06ef-165">In a customer tenant</span></span>  |    <span data-ttu-id="e06ef-166">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-166">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="e06ef-167">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="e06ef-167">woodgrovebank.us</span></span>  |  <span data-ttu-id="e06ef-168">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-168">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="e06ef-169">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-169">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="e06ef-170">Subdominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-170">Subdomain</span></span> | <span data-ttu-id="e06ef-171">En un inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="e06ef-171">In a customer tenant</span></span>   |   <span data-ttu-id="e06ef-172">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-172">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="e06ef-173">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e06ef-173">contoso.com</span></span>   |<span data-ttu-id="e06ef-174">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-174">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="e06ef-175">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-175">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="e06ef-176">Subdominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-176">Subdomain</span></span> | <span data-ttu-id="e06ef-177">En un inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="e06ef-177">In a customer tenant</span></span> |   <span data-ttu-id="e06ef-178">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-178">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="e06ef-179">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="e06ef-179">adventureworks.com</span></span> | <span data-ttu-id="e06ef-180">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-180">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="e06ef-181">Para configurar la base y subdominios, siga los pasos descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="e06ef-181">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="e06ef-182">En el ejemplo, se configurará un nombre de dominio base (customers.adatum.biz) y un subdominio para un cliente (sbc1.customers.adatum.biz en el inquilino de Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="e06ef-182">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="e06ef-183">Registrar un nombre de dominio base en el inquilino de operador</span><span class="sxs-lookup"><span data-stu-id="e06ef-183">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="e06ef-184">**Estas acciones se realizan en el inquilino de operador.**</span><span class="sxs-lookup"><span data-stu-id="e06ef-184">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="e06ef-185">Asegúrese de que tiene los derechos adecuados en el inquilino de operador</span><span class="sxs-lookup"><span data-stu-id="e06ef-185">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="e06ef-186">Sólo se pueden agregar nuevos dominios si ha iniciado sesión el centro de administración de Office 365 como un administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e06ef-186">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="e06ef-187">Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365 (https://portal.office.com), vaya a **los usuarios** > **Usuarios activos**y, a continuación, compruebe que dispone de una función de administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e06ef-187">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="e06ef-188">Para obtener más información acerca de los roles de administrador y cómo asignar una función de Office 365, vea [roles de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="e06ef-188">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="e06ef-189">Agregar un dominio de la base para el inquilino y compruebe</span><span class="sxs-lookup"><span data-stu-id="e06ef-189">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="e06ef-190">En el centro de administración de Microsoft 365, vaya al **programa de instalación** > **dominios** > **Agregue el dominio**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-190">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="e06ef-191">En el cuadro **Escriba un dominio que es propietario** , escriba el FQDN del dominio base.</span><span class="sxs-lookup"><span data-stu-id="e06ef-191">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="e06ef-192">En el siguiente ejemplo, el dominio de la base es *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="e06ef-192">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Adición de un dominio base](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="e06ef-194">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-194">Click **Next**.</span></span>
4. <span data-ttu-id="e06ef-195">En el ejemplo, el inquilino ya tiene adatum.biz como un nombre de dominio comprobado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-195">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="e06ef-196">El asistente no le preguntará para la comprobación adicional debido a que customers.adatum.biz es un subdominio para el nombre ya registrado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-196">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="e06ef-197">Sin embargo, si agrega un FQDN que no se ha comprobado antes, necesitará ir a través del proceso de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e06ef-197">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="e06ef-198">El proceso de comprobación es [se describe a continuación](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="e06ef-198">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Confirmación de un nombre de dominio comprueba](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="e06ef-200">Haga clic en **siguiente**y en la página **Configuración de DNS de actualización** , seleccione **vamos a agregar los registros DNS yo mismo** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-200">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="e06ef-201">En la siguiente página, desactive todos los valores (a menos que desee usar el nombre de dominio de Exchange, SharePoint o equipos/Skype para la empresa), haga clic en **siguiente**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-201">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="e06ef-202">Asegúrese de que su nuevo dominio se encuentra en el estado del programa de instalación completado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-202">Make sure your new domain is in the Setup complete status.</span></span>

    ![Dominios que muestra un estado de la instalación completa](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="e06ef-204">Activar el nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-204">Activate the domain name</span></span>

<span data-ttu-id="e06ef-205">Una vez que haya registrado un nombre de dominio, debe activar mediante la adición de al menos un usuario y asignar una dirección SIP con la parte FQDN de la dirección SIP que coincida con el dominio base creado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-205">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="e06ef-206">*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información acerca de cómo agregar los usuarios en los inquilinos de Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e06ef-206">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="e06ef-207">Por ejemplo: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-207">For example: test@customers.adatum.biz</span></span>

![Página de activación de dominio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="e06ef-209">Registrar un nombre de subdominio en un inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="e06ef-209">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="e06ef-210">Debe crear un nombre de subdominio único para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-210">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="e06ef-211">En este ejemplo, crearemos un subdominio sbc1.customers.adatum.biz en un inquilino con el woodgrovebank.us de nombre de dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e06ef-211">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="e06ef-212">**Todas las acciones que aparece a continuación se encuentran en el inquilino del cliente.**</span><span class="sxs-lookup"><span data-stu-id="e06ef-212">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="e06ef-213">Asegúrese de que tiene los derechos adecuados en el inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="e06ef-213">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="e06ef-214">Sólo se pueden agregar nuevos dominios si ha iniciado sesión el centro de administración de Office 365 como un administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e06ef-214">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="e06ef-215">Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365 (https://portal.office.com), vaya a **los usuarios** > **Usuarios activos**y, a continuación, compruebe que dispone de una función de administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e06ef-215">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="e06ef-216">Para obtener más información acerca de los roles de administrador y cómo asignar una función de Office 365, vea [roles de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="e06ef-216">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="e06ef-217">Agregar un subdominio para el inquilino del cliente y compruebe</span><span class="sxs-lookup"><span data-stu-id="e06ef-217">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="e06ef-218">En el centro de administración de Microsoft 365, vaya al **programa de instalación** > **dominios** > **Agregue el dominio**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-218">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="e06ef-219">En el cuadro **Escriba un dominio que es propietario** , escriba el FQDN del subdominio para este inquilino.</span><span class="sxs-lookup"><span data-stu-id="e06ef-219">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="e06ef-220">En el ejemplo siguiente, el subdominio es sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="e06ef-220">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Adición de un subdominio del cliente](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="e06ef-222">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-222">Click **Next**.</span></span>
4. <span data-ttu-id="e06ef-223">El FQDN nunca se ha registrado en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="e06ef-223">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="e06ef-224">En el siguiente paso, debe comprobar el dominio.</span><span class="sxs-lookup"><span data-stu-id="e06ef-224">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="e06ef-225">Seleccione **Agregar un registro TXT en su lugar**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-225">Select **Add a TXT record instead**.</span></span> 

    ![Opciones en la página comprobar dominio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="e06ef-227">Haga clic en **siguiente**y, tenga en cuenta el valor TXT generado para comprobar el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="e06ef-227">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Registros de texto en la página comprobar dominio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="e06ef-229">Cree el registro TXT con el valor desde el paso anterior en el proveedor de hospedaje de DNS del operador.</span><span class="sxs-lookup"><span data-stu-id="e06ef-229">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Crear el registro TXT en el proveedor de hospedaje de DNS del operador](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="e06ef-231">Para obtener más información, consulte [crear registros DNS en cualquier proveedor de hospedaje de DNS para Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="e06ef-231">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="e06ef-232">Vaya al centro de administración de Microsoft 365 del cliente y haga clic en **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-232">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="e06ef-233">En la página siguiente, seleccione **vamos a agregar los registros DNS yo mismo** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-233">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Opciones en la página de configuración de DNS de actualización](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="e06ef-235">En la página **Elija los servicios en línea** , desactive todas las opciones y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-235">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![La elija la página Servicios en línea](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="e06ef-237">En la página **configuración de actualización de DNS** , haga clic en **Finalizar** .</span><span class="sxs-lookup"><span data-stu-id="e06ef-237">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![La página de configuración de DNS de actualización](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="e06ef-239">Asegúrese de que el estado es **completar el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="e06ef-239">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Página que muestra el estado de la instalación completa](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="e06ef-241">Activar el nombre de subdominio</span><span class="sxs-lookup"><span data-stu-id="e06ef-241">Activate the subdomain name</span></span>

<span data-ttu-id="e06ef-242">Después de registrar un nombre de dominio, debe activar mediante la adición de al menos un usuario y asignar una dirección SIP con la parte FQDN de la dirección SIP que coincidan con el subdominio creado en el inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-242">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="e06ef-243">*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información acerca de cómo agregar los usuarios en los inquilinos de Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e06ef-243">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="e06ef-244">Por ejemplo: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="e06ef-244">For example: test@sbc1.customers.adatum.biz</span></span>

![Activación de la página de subdominio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="e06ef-246">Crear usuarios de un tronco y aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e06ef-246">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="e06ef-247">En función de los comentarios que recibimos en el programa de adopción técnica, Microsoft podría cambiar el proceso de creación de troncos en los inquilinos de atención al cliente para simplificar el proceso.</span><span class="sxs-lookup"><span data-stu-id="e06ef-247">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="e06ef-248">Por favor, vea las actualizaciones de documentación de esta página y siga los blogs de la comunidad técnica de Microsoft para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e06ef-248">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="e06ef-249">Crear un tronco en el dominio de cliente mediante el comando New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="e06ef-249">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="e06ef-250">El tronco FQDN **debe** coincidir con el subdominio creado para el cliente.</span><span class="sxs-lookup"><span data-stu-id="e06ef-250">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="e06ef-251">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e06ef-251">For example:</span></span>

<span data-ttu-id="e06ef-252">*Nuevo-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz - SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="e06ef-252">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="e06ef-253">Abastecer a los usuarios con los números de teléfono y configuración de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="e06ef-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="e06ef-254">Para obtener más información sobre el nuevo-CSOnlinePSTNGateway, aprovisionamiento a los usuarios y la configuración de enrutamiento de voz, consulte [Configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e06ef-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="e06ef-255">Consulte las [instrucciones del proveedor SBC](#deploy-and-configure-the-sbc) sobre la configuración de enviar el nombre FQDN de subdominios en el encabezado de contacto.</span><span class="sxs-lookup"><span data-stu-id="e06ef-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

