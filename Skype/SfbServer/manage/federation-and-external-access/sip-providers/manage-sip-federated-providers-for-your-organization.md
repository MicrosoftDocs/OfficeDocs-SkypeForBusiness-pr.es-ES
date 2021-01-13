---
title: Administrar proveedores federados SIP para la organización
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre cómo configurar la compatibilidad con usuarios de proveedores federados SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823570"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="09b89-103">Administrar proveedores federados SIP para su organización en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="09b89-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="09b89-104">Para configurar la admisión de los usuarios de proveedores federados de SIP, realice las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="09b89-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="09b89-105">Configurar una o varias directivas de acceso de usuarios externos para admitir la comunicación con los contactos de proveedores federados de SIP</span><span class="sxs-lookup"><span data-stu-id="09b89-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="09b89-106">Especificar los proveedores hospedados que desea admitir</span><span class="sxs-lookup"><span data-stu-id="09b89-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="09b89-107">Especificar los proveedores de MI públicos que desea admitir</span><span class="sxs-lookup"><span data-stu-id="09b89-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="09b89-108">Crear o editar proveedores federados SIP públicos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="09b89-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="09b89-109">La conectividad de mensajería instantánea (MI) pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="09b89-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="09b89-110">Skype Empresarial Server tiene configuraciones de proveedor público para mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="09b89-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="09b89-111">Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de comprobación predeterminado Permite a los usuarios comunicarse solo con personas de su lista de contactos que usan **este proveedor.**</span><span class="sxs-lookup"><span data-stu-id="09b89-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="09b89-112">Como configuración predeterminada, no está habilitado ninguno de los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="09b89-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="09b89-113">Debe rellenar el contrato de licencia y proporcionar el trabajo antes de habilitar los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="09b89-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="09b89-114">Puede habilitar al proveedor antes de completar la licencia y proporcionar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="09b89-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="09b89-115">Los usuarios no podrán comunicarse con los contactos de estos proveedores hasta que haya finalizado el trabajo como requisito previo.</span><span class="sxs-lookup"><span data-stu-id="09b89-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="09b89-116">Para obtener información detallada sobre la concesión de licencias y el aprovisionamiento de proveedores públicos, vea Configurar directivas para controlar la [obtención de acceso de usuarios públicos.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="09b89-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="09b89-117">Use el siguiente procedimiento para crear o editar proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="09b89-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="09b89-118">Para crear o cambiar proveedores públicos</span><span class="sxs-lookup"><span data-stu-id="09b89-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="09b89-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="09b89-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09b89-120">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09b89-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09b89-121">En el barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.</span><span class="sxs-lookup"><span data-stu-id="09b89-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="09b89-122">Si necesita crear un nuevo proveedor público, haga clic en **Nuevo** y luego en **Proveedor público**.</span><span class="sxs-lookup"><span data-stu-id="09b89-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="09b89-123">Si desea cambiar una entrada de la lista de los proveedores públicos, seleccione un proveedor público, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="09b89-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="09b89-124">En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="09b89-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="09b89-125">**Habilitar comunicaciones con este proveedor:**    la selección de este parámetro permite la mensajería instantánea con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="09b89-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="09b89-126">**Nombre del proveedor:**    Una propiedad necesaria, escriba el nombre del proveedor como se reflejará en el listado de Proveedores federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="09b89-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="09b89-127">**Servicio perimetral de acceso (FQDN):**   Una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando.</span><span class="sxs-lookup"><span data-stu-id="09b89-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="09b89-128">Esta información se proporciona como un elemento predeterminado y debe cambiarse solo si el proveedor cambia el FQDN del servicio perimetral de acceso en el proveedor de público.</span><span class="sxs-lookup"><span data-stu-id="09b89-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="09b89-129">**Nivel de comprobación predeterminado:**    el parámetro predeterminado, **Permitir a los usuarios comunicarse con las personas de su lista de contactos que usan este proveedor** limitará la comunicación a los contactos que han aceptado y están en la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="09b89-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="09b89-p104">La activación de **Permitir a los usuarios comunicarse con todos los que usan este proveedor** elimina la restricción que debe haber recibido y aceptado como una invitación de contacto. Este parámetro no limita quién puede comunicarse con usted desde la red del proveedor público.</span><span class="sxs-lookup"><span data-stu-id="09b89-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="09b89-132">Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="09b89-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="09b89-133">Crear o editar proveedores federados SIP hospedados en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="09b89-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="09b89-134">La conectividad de mensajería instantánea (MI) del proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="09b89-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="09b89-135">Cada proveedor hospedado se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **Permitir a los usuarios comunicarse solamente con personas de su Lista de contactos que utilizan este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="09b89-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="09b89-136">Use el siguiente procedimiento para crear o editar proveedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="09b89-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="09b89-137">Para crear o editar proveedores hospedados</span><span class="sxs-lookup"><span data-stu-id="09b89-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="09b89-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="09b89-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09b89-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09b89-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="09b89-140">En el barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, en **Proveedores federados de SIP**.</span><span class="sxs-lookup"><span data-stu-id="09b89-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="09b89-141">Si necesita crear un nuevo proveedor hospedado, haga clic en **Nuevo** y, a continuación, haga clic en **Proveedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="09b89-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="09b89-142">Si necesita editar una entrada de la lista de Proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="09b89-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="09b89-143">En la página **Editar proveedor federado de SIP**, puede escribir o editar la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="09b89-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="09b89-144">**Habilitar comunicaciones con este proveedor**   Al seleccionar esta configuración se habilita la comunicación con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="09b89-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="09b89-145">**Nombre del proveedor:**    Una propiedad necesaria, escriba el nombre del proveedor como se reflejará en el listado de Proveedores federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="09b89-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="09b89-146">**Servicio perimetral de acceso (FQDN):**   Una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando.</span><span class="sxs-lookup"><span data-stu-id="09b89-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="09b89-147">Esta información debe ser proporcionada por el proveedor hospedado y solo debe modificarse si el proveedor hospedado realiza un cambio al FQDN del servicio perimetral de acceso del proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="09b89-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="09b89-148">**Nivel de verificación predeterminado:**    La configuración predeterminada, **Permitir a los usuarios comunicarse con personas de su Lista de contactos que utilizan este proveedor**, limitará la comunicación a los contactos que haya aceptado y estén en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="09b89-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="09b89-p106">Seleccionar **Permitir a los usuarios comunicarse con todos los que utilizan este proveedor** elimina la restricción de tener que haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede contactarlo desde la red del proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="09b89-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="09b89-151">Cuando haya terminado de configurar los parámetros, haga clic en **Confirmar** para guardar o haga clic en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="09b89-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="09b89-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09b89-152">See Also</span></span>


[<span data-ttu-id="09b89-153">Configurar directivas para controlar la a acces de usuarios públicos</span><span class="sxs-lookup"><span data-stu-id="09b89-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="09b89-154">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="09b89-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

