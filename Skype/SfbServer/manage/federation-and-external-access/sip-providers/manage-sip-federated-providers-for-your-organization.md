---
title: Administrar proveedores federados SIP para la organización
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Aprenda a configurar soporte técnico para los usuarios de proveedores federados de SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818371"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="869ba-103">Administrar proveedores federados de SIP para su organización en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="869ba-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="869ba-104">Para configurar el soporte técnico a los usuarios de proveedores federados de SIP, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="869ba-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="869ba-105">Configurar una o más directivas de acceso de usuarios externos para admitir la comunicación con contactos de proveedores federados de SIP</span><span class="sxs-lookup"><span data-stu-id="869ba-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="869ba-106">Especificar qué proveedores alojados desea admitir</span><span class="sxs-lookup"><span data-stu-id="869ba-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="869ba-107">Especificar los proveedores de mensajería instantánea pública que desea admitir</span><span class="sxs-lookup"><span data-stu-id="869ba-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="869ba-108">Crear o editar proveedores federados de SIP pública en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="869ba-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="869ba-109">La conectividad de mensajería instantánea pública (mi) permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="869ba-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="869ba-110">Skype empresarial Server tiene configuraciones de proveedor público para la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="869ba-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="869ba-111">Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="869ba-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="869ba-112">Como configuración predeterminada, ninguno de los proveedores públicos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="869ba-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="869ba-113">Debe completar el contrato de licencia y el aprovisionamiento antes de habilitar los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="869ba-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="869ba-114">Puede habilitar el proveedor antes de completar el trabajo de licencias y aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="869ba-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="869ba-115">Los usuarios no podrán comunicarse con los contactos de esos proveedores hasta que se haya completado el trabajo previo.</span><span class="sxs-lookup"><span data-stu-id="869ba-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="869ba-116">Para obtener más información sobre las licencias y el aprovisionamiento de proveedores públicos, vea [configurar directivas para controlar el accesible a los usuarios públicos](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="869ba-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="869ba-117">Use el procedimiento siguiente para crear o editar proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="869ba-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="869ba-118">Para crear o editar proveedores públicos</span><span class="sxs-lookup"><span data-stu-id="869ba-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="869ba-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="869ba-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="869ba-120">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="869ba-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="869ba-121">En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en **proveedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="869ba-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="869ba-122">Si necesita crear un proveedor público nuevo, haga clic en **nuevo** y, a continuación, haga clic en **proveedor público**.</span><span class="sxs-lookup"><span data-stu-id="869ba-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="869ba-123">Si necesita modificar una entrada de la lista de proveedores públicos, seleccione un proveedor público, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="869ba-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="869ba-124">En la página **Editar proveedor federado de SIP** , puede escribir o modificar las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="869ba-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="869ba-125">**Habilitar las comunicaciones con este proveedor**   al seleccionar esta opción, se habilita la mensajería instantánea con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="869ba-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="869ba-126">**Nombre del proveedor:**   una propiedad obligatoria, escriba el nombre del proveedor, ya que se reflejará en la lista de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="869ba-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="869ba-127">**Servicio perimetral de acceso (FQDN):**   una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando.</span><span class="sxs-lookup"><span data-stu-id="869ba-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="869ba-128">Esta información se proporciona como un elemento predeterminado y solo se debe cambiar si el proveedor público realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor público.</span><span class="sxs-lookup"><span data-stu-id="869ba-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="869ba-129">**Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir que los usuarios se comuniquen con personas de su lista de contactos que usan este proveedor** , limitará la comunicación a los contactos que haya aceptado y estarán en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="869ba-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="869ba-130">Si selecciona **permitir que los usuarios se comuniquen con todos los usuarios con este proveedor** , se eliminará la restricción que debe haber recibido y aceptado una invitación de contacto.</span><span class="sxs-lookup"><span data-stu-id="869ba-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="869ba-131">Esta configuración no limita quién puede comunicarse contigo desde la red del proveedor público.</span><span class="sxs-lookup"><span data-stu-id="869ba-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="869ba-132">Cuando haya terminado de configurar la configuración, haga clic en **confirmar** para guardar o en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="869ba-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="869ba-133">Crear o editar proveedores federados de SIP alojados en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="869ba-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="869ba-134">La conectividad de mensajería instantánea (mi) de proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="869ba-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="869ba-135">Cada proveedor alojado se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="869ba-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="869ba-136">Use el procedimiento siguiente para crear o editar proveedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="869ba-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="869ba-137">Para crear o editar proveedores hospedados</span><span class="sxs-lookup"><span data-stu-id="869ba-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="869ba-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="869ba-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="869ba-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="869ba-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="869ba-140">En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en **proveedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="869ba-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="869ba-141">Si necesita crear un nuevo proveedor alojado, haga clic en **nuevo** y, a continuación, haga clic en **proveedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="869ba-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="869ba-142">Si necesita modificar una entrada de la lista de proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="869ba-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="869ba-143">En la página **Editar proveedor federado de SIP** , puede escribir o modificar las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="869ba-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="869ba-144">**Habilitar las comunicaciones con este proveedor**   al seleccionar esta opción se habilitan las comunicaciones con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="869ba-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="869ba-145">**Nombre del proveedor:**   una propiedad obligatoria, escriba el nombre del proveedor, ya que se reflejará en la lista de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="869ba-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="869ba-146">**Servicio perimetral de acceso (FQDN):**   una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando.</span><span class="sxs-lookup"><span data-stu-id="869ba-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="869ba-147">Esta información debe proporcionarla el proveedor hospedado y solo se debe cambiar si el proveedor hospedado realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="869ba-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="869ba-148">**Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir que los usuarios se comuniquen con personas de su lista de contactos que usan este proveedor** , limitará la comunicación a los contactos que haya aceptado y estarán en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="869ba-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="869ba-149">Si selecciona **permitir que los usuarios se comuniquen con todos los usuarios con este proveedor** , se eliminará la restricción que debe haber recibido y aceptado una invitación de contacto.</span><span class="sxs-lookup"><span data-stu-id="869ba-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="869ba-150">Esta configuración no limita quién puede ponerse en contacto contigo desde la red del proveedor alojado.</span><span class="sxs-lookup"><span data-stu-id="869ba-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="869ba-151">Cuando haya terminado de configurar la configuración, haga clic en **confirmar** para guardar o en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="869ba-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="869ba-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="869ba-152">See Also</span></span>


[<span data-ttu-id="869ba-153">Configurar directivas para controlar el accesible al usuario público</span><span class="sxs-lookup"><span data-stu-id="869ba-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="869ba-154">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="869ba-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

