---
title: Administrar proveedores federados SIP para la organización
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo configurar la admisión de proveedores federados de los usuarios de SIP.
ms.openlocfilehash: 1259ae9d2dfd7d829caaa6dba714f0876b5500c4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197838"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="de954-103">Administrar los proveedores federados SIP para su organización en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="de954-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="de954-104">Para configurar la compatibilidad para los usuarios de SIP proveedores federados, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de954-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="de954-105">Configurar una o varias directivas de acceso de usuarios externos para admitir la comunicación con los contactos de proveedores federados SIP</span><span class="sxs-lookup"><span data-stu-id="de954-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="de954-106">Especificar los proveedores hospedados que desea admitir</span><span class="sxs-lookup"><span data-stu-id="de954-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="de954-107">Especificar los proveedores de mensajería instantánea públicos que desea admitir</span><span class="sxs-lookup"><span data-stu-id="de954-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="de954-108">Crear o editar proveedores federados SIP pública en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="de954-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="de954-109">Conectividad de mensajería instantánea pública permite a los usuarios de su organización utilizar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="de954-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="de954-110">Skype para Business Server tiene las configuraciones de proveedor público para la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="de954-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="de954-111">Cada proveedor público se configura con el nombre de dominio completo de servidor perimetral del proveedor y el nivel de comprobación predeterminado **Permitir a los usuarios comunicarse únicamente con las personas en su lista de contactos que usa este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="de954-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="de954-112">Como un valor predeterminado, ninguno de los proveedores públicos están habilitada.</span><span class="sxs-lookup"><span data-stu-id="de954-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="de954-113">Debe completar el contrato de licencia y el aprovisionamiento de trabajo antes de habilitar a los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="de954-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="de954-114">Puede habilitar al proveedor antes de completar la concesión de licencias y trabajo de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="de954-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="de954-115">Los usuarios no podrán comunicarse con los contactos en esos proveedores hasta que se complete el trabajo de requisito previos.</span><span class="sxs-lookup"><span data-stu-id="de954-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="de954-116">Para obtener información detallada sobre licencias y aprovisionamiento de los proveedores públicos, vea [Configurar directivas para controlar el acceso de usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="de954-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="de954-117">Use el procedimiento siguiente para crear o cambiar proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="de954-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="de954-118">Para crear o editar proveedores públicos</span><span class="sxs-lookup"><span data-stu-id="de954-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="de954-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="de954-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de954-120">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="de954-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de954-121">En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Proveedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="de954-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="de954-122">Si necesita crear un nuevo proveedor público, haga clic en **nuevo** y, a continuación, haga clic en **proveedor público**.</span><span class="sxs-lookup"><span data-stu-id="de954-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="de954-123">Si necesita editar una entrada de la lista de proveedores públicos, seleccione un proveedor público, haga clic en **Editar**, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="de954-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="de954-124">En la página **Editar proveedor SIP federado** , puede escribir o editar los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="de954-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="de954-125">**Habilitar las comunicaciones con este proveedor**   al seleccionar esta configuración permite la mensajería instantánea con usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="de954-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="de954-126">**Nombre del proveedor:**   una propiedad necesaria, el tipo, el nombre del proveedor como se reflejará en el listado de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="de954-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="de954-127">**Servicio perimetral (FQDN) de acceso:**   una propiedad necesaria, escriba el nombre de dominio completo del servicio de servidor perimetral de acceso del proveedor del que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="de954-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="de954-128">Esta información se proporciona como un elemento de forma predeterminada y sólo se puede cambiar si el proveedor público realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor público.</span><span class="sxs-lookup"><span data-stu-id="de954-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="de954-129">**Nivel de comprobación predeterminado:**   la configuración predeterminada, **Permitir a los usuarios comunicarse con personas en su lista de contactos que usa este proveedor** limitará la comunicación a los contactos que se han aceptado y se encuentran en la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="de954-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="de954-130">Selección de **Permitir a los usuarios comunicarse con todos los usuarios con este proveedor** , quita la restricción que debe ha recibido y aceptado una invitación de contacto.</span><span class="sxs-lookup"><span data-stu-id="de954-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="de954-131">Esta opción no limitar quién puede en contacto con usted desde la red del proveedor público.</span><span class="sxs-lookup"><span data-stu-id="de954-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="de954-132">Cuando haya configurar las opciones, haga clic en **Confirmar** para guardar, o haga clic en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="de954-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="de954-133">Crear o editar proveedores SIP federado hospedados en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="de954-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="de954-134">Hospedado proveedor (IM) conectividad permite a los usuarios de la organización para usar la mensajería instantánea para comunicarse con los usuarios de servicios de mensajería instantánea proporcionados por proveedores hospedados de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="de954-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="de954-135">Cada proveedor hospedado está configurado con el nombre de dominio completo de servidor perimetral del proveedor y el nivel de comprobación predeterminado **Permitir a los usuarios comunicarse únicamente con las personas en su lista de contactos que usa este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="de954-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="de954-136">Utilice el procedimiento siguiente para crear o editar proveedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="de954-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="de954-137">Para crear o editar proveedores hospedados</span><span class="sxs-lookup"><span data-stu-id="de954-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="de954-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="de954-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de954-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="de954-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de954-140">En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Proveedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="de954-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="de954-141">Si necesita crear un nuevo proveedor hospedado, haga clic en **nuevo** y, a continuación, haga clic en **proveedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="de954-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="de954-142">Si necesita editar una entrada de la lista de proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar**, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="de954-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="de954-143">En la página **Editar proveedor SIP federado** , puede escribir o editar los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="de954-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="de954-144">**Habilitar las comunicaciones con este proveedor**   al seleccionar esta configuración habilita la comunicación con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="de954-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="de954-145">**Nombre del proveedor:**   una propiedad necesaria, el tipo, el nombre del proveedor como se reflejará en el listado de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="de954-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="de954-146">**Servicio perimetral (FQDN) de acceso:**   una propiedad necesaria, escriba el nombre de dominio completo del servicio de servidor perimetral de acceso del proveedor hospedado que está configurando.</span><span class="sxs-lookup"><span data-stu-id="de954-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="de954-147">Esta información debe ser proporcionada por el proveedor hospedado y sólo se puede cambiar si el proveedor hospedado realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="de954-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="de954-148">**Nivel de comprobación predeterminado:**   la configuración predeterminada, **Permitir a los usuarios comunicarse con personas en su lista de contactos que usa este proveedor** limitará la comunicación a los contactos que se han aceptado y se encuentran en la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="de954-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="de954-149">Selección de **Permitir a los usuarios comunicarse con todos los usuarios con este proveedor** , quita la restricción que debe ha recibido y aceptado una invitación de contacto.</span><span class="sxs-lookup"><span data-stu-id="de954-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="de954-150">Esta opción no limitar quién puede en contacto con usted desde la red del proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="de954-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="de954-151">Cuando haya configurar las opciones, haga clic en **Confirmar** para guardar, o haga clic en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="de954-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="de954-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de954-152">See Also</span></span>


[<span data-ttu-id="de954-153">Configurar directivas para controlar el acceso de usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="de954-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="de954-154">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="de954-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

