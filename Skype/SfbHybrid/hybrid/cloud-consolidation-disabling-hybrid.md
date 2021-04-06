---
title: Deshabilitar la implementación híbrida para completar la migración a la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: En este artículo se incluyen pasos detallados para deshabilitar la implementación híbrida como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: 5528172c6a9309a0884c9417a64da589f0f0d4a4
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593858"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a><span data-ttu-id="72ec0-103">Deshabilitar la configuración híbrida para completar la migración a la nube</span><span class="sxs-lookup"><span data-stu-id="72ec0-103">Disable your hybrid configuration to complete migration to the cloud</span></span>

<span data-ttu-id="72ec0-104">En este artículo se describe cómo deshabilitar la configuración híbrida antes de retirar el entorno local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="72ec0-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="72ec0-105">Este es el paso 2 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="72ec0-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="72ec0-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="72ec0-106">Step 1.</span></span> <span data-ttu-id="72ec0-107">[Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="72ec0-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="72ec0-108">**Paso 2. Deshabilite la configuración híbrida.**</span><span class="sxs-lookup"><span data-stu-id="72ec0-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="72ec0-109">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="72ec0-109">(This article)</span></span>

- <span data-ttu-id="72ec0-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="72ec0-110">Step 3.</span></span> <span data-ttu-id="72ec0-111">[Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="72ec0-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="overview"></a><span data-ttu-id="72ec0-112">Información general</span><span class="sxs-lookup"><span data-stu-id="72ec0-112">Overview</span></span>

<span data-ttu-id="72ec0-113">Después de actualizar todos los usuarios de Skype Empresarial local a Teams Solo en Microsoft 365, puede retirar la implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="72ec0-113">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="72ec0-114">Antes de retirar la implementación local de Skype Empresarial y quitar cualquier hardware, debe separar lógicamente la implementación local de Microsoft 365 deshabilitando la implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="72ec0-114">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="72ec0-115">La deshabilitación híbrida consta de los tres pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="72ec0-115">Disabling hybrid consists of the following three steps:</span></span>

1. <span data-ttu-id="72ec0-116">Actualizar los registros DNS para que apunten a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72ec0-116">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="72ec0-117">Deshabilite el espacio de direcciones sip compartido (también conocido como "dominio dividido") en la organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72ec0-117">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

3. <span data-ttu-id="72ec0-118">Deshabilite la capacidad de comunicarse localmente con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72ec0-118">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="72ec0-119">Estos pasos separan lógicamente la implementación local de Skype Empresarial Server de Microsoft 365 y deben realizarse conjuntamente como una unidad.</span><span class="sxs-lookup"><span data-stu-id="72ec0-119">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and should be done together as a unit.</span></span> <span data-ttu-id="72ec0-120">Los detalles de cada paso se proporcionan en este artículo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-120">Details for each step are provided in this article.</span></span> <span data-ttu-id="72ec0-121">Una vez completado, puede retirar la implementación local de Skype Empresarial mediante uno de los dos métodos a los que se hace referencia a continuación.</span><span class="sxs-lookup"><span data-stu-id="72ec0-121">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="72ec0-122">Una vez completada esta separación lógica, los atributos msRTCSIP de su Active Directory local siguen teniendo valores y seguirán sincroniciendo a través de Azure AD Connect en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72ec0-122">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="72ec0-123">La forma de retirar el entorno local depende de si desea dejar estos atributos en su lugar o, en primer lugar, borrarlos de su Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-123">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="72ec0-124">Tenga en cuenta que borrar los atributos msRTCSIP locales después de migrar desde local podría provocar la pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-124">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="72ec0-125">Más adelante, se describen los detalles y las transacciones de los dos enfoques de retirada.</span><span class="sxs-lookup"><span data-stu-id="72ec0-125">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="72ec0-126">Pasos detallados</span><span class="sxs-lookup"><span data-stu-id="72ec0-126">Detailed Steps</span></span>

1. <span data-ttu-id="72ec0-127">*Actualice DNS para que apunte a Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="72ec0-127">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="72ec0-128">El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype Empresarial apunten a Microsoft 365 en lugar de a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-128">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="72ec0-129">En particular:</span><span class="sxs-lookup"><span data-stu-id="72ec0-129">Specifically:</span></span>

    |<span data-ttu-id="72ec0-130">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="72ec0-130">Record type</span></span>|<span data-ttu-id="72ec0-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="72ec0-131">Name</span></span>|<span data-ttu-id="72ec0-132">TTL</span><span class="sxs-lookup"><span data-stu-id="72ec0-132">TTL</span></span>|<span data-ttu-id="72ec0-133">Valor</span><span class="sxs-lookup"><span data-stu-id="72ec0-133">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="72ec0-134">SRV</span><span class="sxs-lookup"><span data-stu-id="72ec0-134">SRV</span></span>|<span data-ttu-id="72ec0-135">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="72ec0-135">_sipfederationtls._tcp</span></span>|<span data-ttu-id="72ec0-136">3600</span><span class="sxs-lookup"><span data-stu-id="72ec0-136">3600</span></span>|<span data-ttu-id="72ec0-137">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="72ec0-137">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="72ec0-138">SRV</span><span class="sxs-lookup"><span data-stu-id="72ec0-138">SRV</span></span>|<span data-ttu-id="72ec0-139">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="72ec0-139">_sip._tls</span></span>|<span data-ttu-id="72ec0-140">3600</span><span class="sxs-lookup"><span data-stu-id="72ec0-140">3600</span></span>|<span data-ttu-id="72ec0-141">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="72ec0-141">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="72ec0-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="72ec0-142">CNAME</span></span>| <span data-ttu-id="72ec0-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="72ec0-143">lyncdiscover</span></span>|   <span data-ttu-id="72ec0-144">3600</span><span class="sxs-lookup"><span data-stu-id="72ec0-144">3600</span></span>|   <span data-ttu-id="72ec0-145">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="72ec0-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="72ec0-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="72ec0-146">CNAME</span></span>| <span data-ttu-id="72ec0-147">sip</span><span class="sxs-lookup"><span data-stu-id="72ec0-147">sip</span></span>|    <span data-ttu-id="72ec0-148">3600</span><span class="sxs-lookup"><span data-stu-id="72ec0-148">3600</span></span>|   <span data-ttu-id="72ec0-149">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="72ec0-149">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="72ec0-150">Además, se pueden eliminar los registros CNAME para meet o dialin (si están presentes).</span><span class="sxs-lookup"><span data-stu-id="72ec0-150">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="72ec0-151">Por último, se deben quitar los registros DNS de Skype Empresarial en la red interna.</span><span class="sxs-lookup"><span data-stu-id="72ec0-151">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="72ec0-152">En raras ocasiones, cambiar DNS de apuntar localmente a Microsoft 365 para su organización puede provocar que la federación con otras organizaciones deje de funcionar hasta que otra organización actualice su configuración de federación:</span><span class="sxs-lookup"><span data-stu-id="72ec0-152">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="72ec0-153">Las organizaciones federadas que usan el modelo de federación directa anterior (también conocido como Servidor de partners permitidos) tendrán que actualizar las entradas de dominio permitidas para su organización para quitar el FQDN de proxy.</span><span class="sxs-lookup"><span data-stu-id="72ec0-153">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="72ec0-154">Este modelo de federación heredado no se basa en registros SRV de DNS, por lo que dicha configuración se desatendrán una vez que la organización se mueva a la nube.</span><span class="sxs-lookup"><span data-stu-id="72ec0-154">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="72ec0-155">Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync. <span> com tendrá que actualizar su configuración para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-155">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="72ec0-156">Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea.</span><span class="sxs-lookup"><span data-stu-id="72ec0-156">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="72ec0-157">En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="72ec0-157">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="72ec0-158">Si sospecha que alguno de sus socios federados puede estar usando Direct Federation o no haber federado con ninguna organización híbrida o en línea, le sugerimos que envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.</span><span class="sxs-lookup"><span data-stu-id="72ec0-158">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="72ec0-159">*Deshabilitar el espacio de direcciones sip compartido en la organización de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="72ec0-159">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="72ec0-160">El siguiente comando debe realizarse desde una ventana de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="72ec0-160">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="72ec0-161">*Deshabilite la capacidad de comunicarse localmente con Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="72ec0-161">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="72ec0-162">El siguiente comando debe realizarse desde una ventana de PowerShell local:</span><span class="sxs-lookup"><span data-stu-id="72ec0-162">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="72ec0-163">Administración de atributos después de mover usuarios de local a la nube</span><span class="sxs-lookup"><span data-stu-id="72ec0-163">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="72ec0-164">De forma predeterminada, todos los usuarios que se habilitaron anteriormente para Skype Empresarial Server y que posteriormente se movieron a la nube aún tienen atributos msRTCSIP configurados en active directory local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-164">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="72ec0-165">Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono potencialmente (msRTCSIP-Line), siguen sincroniciendo en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72ec0-165">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="72ec0-166">Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72ec0-166">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="72ec0-167">Sin embargo, una vez que se haya quitado la implementación de Skype Empresarial Server, las herramientas de Skype Empresarial Server no estarán disponibles para administrar estos atributos.</span><span class="sxs-lookup"><span data-stu-id="72ec0-167">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="72ec0-168">Hay dos opciones disponibles para controlar esta situación:</span><span class="sxs-lookup"><span data-stu-id="72ec0-168">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="72ec0-169">Deje los usuarios habilitados para cuentas de servidor de Skype Empresarial tal como están y administre los atributos msRTCSIP con herramientas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72ec0-169">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="72ec0-170">Esto garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar fácilmente la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-170">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="72ec0-171">Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.</span><span class="sxs-lookup"><span data-stu-id="72ec0-171">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="72ec0-172">Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea.</span><span class="sxs-lookup"><span data-stu-id="72ec0-172">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="72ec0-173">Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos, pero puede provocar una pérdida temporal del servicio durante el proceso de retirada local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-173">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="72ec0-174">Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory</span><span class="sxs-lookup"><span data-stu-id="72ec0-174">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="72ec0-175">Los administradores pueden administrar usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-175">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="72ec0-176">Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en Active Directory local), debe hacerlo en Active Directory local y permitir que los valores fluyan hasta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72ec0-176">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="72ec0-177">Esto NO requiere Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="72ec0-177">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="72ec0-178">En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72ec0-178">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="72ec0-179">Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:</span><span class="sxs-lookup"><span data-stu-id="72ec0-179">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="72ec0-180">Para modificar la dirección sip de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo .</span><span class="sxs-lookup"><span data-stu-id="72ec0-180">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="72ec0-181">Tenga en cuenta que si el atributo contiene una dirección sip, actualice `ProxyAddresses` también ese valor como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="72ec0-181">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="72ec0-182">Aunque O365 omite la dirección sip si está rellenada, otros componentes locales pueden `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` usarla.</span><span class="sxs-lookup"><span data-stu-id="72ec0-182">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="72ec0-183">Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.</span><span class="sxs-lookup"><span data-stu-id="72ec0-183">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Herramienta de equipos y usuarios de Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="72ec0-185">Si el usuario no tenía originalmente un valor para local antes del movimiento, puede modificar el número de teléfono mediante el parámetro - en el `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) del módulo PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="72ec0-185">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="72ec0-186">Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="72ec0-186">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="72ec0-187">Si se siente cómodo con la combinación de estos métodos, así como con dejar los atributos msRTCSIP en su Active Directory local, simplemente puede volver a crear una imagen de los servidores locales de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="72ec0-187">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="72ec0-188">Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.</span><span class="sxs-lookup"><span data-stu-id="72ec0-188">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="72ec0-189">Método 2: Borrar atributos de Skype Empresarial para todos los usuarios locales de Active Directory</span><span class="sxs-lookup"><span data-stu-id="72ec0-189">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="72ec0-190">Esta opción requiere un esfuerzo adicional y una planeación adecuada, ya que los usuarios que se movieron previamente de un Skype Empresarial Server local a la nube deben volver a aprovisionarse.</span><span class="sxs-lookup"><span data-stu-id="72ec0-190">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="72ec0-191">Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin sistema telefónico y usuarios con sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="72ec0-191">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="72ec0-192">Los usuarios con sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube.</span><span class="sxs-lookup"><span data-stu-id="72ec0-192">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="72ec0-193">**Se recomienda realizar un piloto en el que participen un número reducido de usuarios con sistema telefónico antes de iniciar operaciones masivas de usuario.**</span><span class="sxs-lookup"><span data-stu-id="72ec0-193">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="72ec0-194">Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-194">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="72ec0-195">Este proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="72ec0-195">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="72ec0-196">Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.</span><span class="sxs-lookup"><span data-stu-id="72ec0-196">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="72ec0-197">Si ha configurado puntos de conexión de aplicaciones híbridas locales para operadores automáticos o colas de llamadas, asegúrese de mover estos extremos a Microsoft 365 antes de retirar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="72ec0-197">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="72ec0-198">Confirme que el siguiente cmdlet local de PowerShell de Skype Empresarial devuelve un resultado vacío.</span><span class="sxs-lookup"><span data-stu-id="72ec0-198">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="72ec0-199">Un resultado vacío significa que ningún usuario está internamente y se ha movido a Microsoft 365 o se ha deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="72ec0-199">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="72ec0-200">Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada, ejecutando el siguiente cmdlet local de PowerShell de Skype Empresarial Server para exportar datos de usuario:</span><span class="sxs-lookup"><span data-stu-id="72ec0-200">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="72ec0-201">Antes de continuar, abra SfbUserSettings.csv archivo y confirme que todos los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="72ec0-201">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="72ec0-202">Se recomienda conservar una copia de este archivo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-202">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="72ec0-203">No use este archivo en los siguientes pasos para procesar usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-203">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="72ec0-204">Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="72ec0-204">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="72ec0-205">Después de que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-205">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="72ec0-206">En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente, pero puede filtrar por usuarios en función de criterios que coincidan con la forma en que desea procesar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-206">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="72ec0-207">Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="72ec0-207">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="72ec0-208">Necesitará LineUri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="72ec0-208">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="72ec0-209">Elimine la información de atributo relacionada con Skype Empresarial Server de Active Directory para el conjunto de usuarios que está listo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="72ec0-209">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="72ec0-210">Hay dos pasos para este proceso, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="72ec0-210">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="72ec0-211">Después del siguiente ciclo de sincronización de AAD después de ejecutar este paso, los usuarios con sistema telefónico que se movieron previamente de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete correctamente y se confirme en el paso 9.</span><span class="sxs-lookup"><span data-stu-id="72ec0-211">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="72ec0-212">Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.</span><span class="sxs-lookup"><span data-stu-id="72ec0-212">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="72ec0-213">A continuación, para el mismo conjunto de usuarios, desactive el valor de msRTCSIP-DeploymentLocator con PowerShell de Active Directory local:</span><span class="sxs-lookup"><span data-stu-id="72ec0-213">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="72ec0-214">Ejecute el siguiente cmdlet local de PowerShell de Skype Empresarial para agregar el valor de la dirección sip al proxy de Active Directory localAddresses.</span><span class="sxs-lookup"><span data-stu-id="72ec0-214">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="72ec0-215">Esto evitará problemas de interoperabilidad que dependen de este atributo.</span><span class="sxs-lookup"><span data-stu-id="72ec0-215">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="72ec0-216">Ejecutar Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="72ec0-216">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="72ec0-217">Espere a que se complete el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-217">Wait for user provisioning to complete.</span></span> <span data-ttu-id="72ec0-218">Puede supervisar el progreso del aprovisionamiento de usuarios ejecutando el siguiente comando de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="72ec0-218">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="72ec0-219">El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="72ec0-219">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="72ec0-220">Ejecute el siguiente comando de PowerShell de Skype Empresarial Online para asignar números de teléfono y habilitar a los usuarios para el sistema telefónico:</span><span class="sxs-lookup"><span data-stu-id="72ec0-220">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="72ec0-221">Si todavía tiene puntos de conexión de Skype Empresarial (ya sea clientes de Skype o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true.</span><span class="sxs-lookup"><span data-stu-id="72ec0-221">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="72ec0-222">Si su organización solo usa puntos de conexión de Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-222">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="72ec0-223">Confirme que los usuarios con funcionalidad del sistema telefónico se han aprovisionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="72ec0-223">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="72ec0-224">El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="72ec0-224">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="72ec0-225">Repita los pasos del 3 al 9 hasta que se procese a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="72ec0-225">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="72ec0-226">Confirme que todos los usuarios se han procesado correctamente ejecutando los dos comandos de PowerShell siguientes.</span><span class="sxs-lookup"><span data-stu-id="72ec0-226">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="72ec0-227">Comando de PowerShell local de Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="72ec0-227">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="72ec0-228">Comando de PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="72ec0-228">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="72ec0-229">Después de completar todos los pasos del método 2, consulte [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) para obtener pasos adicionales para quitar la implementación local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="72ec0-229">After you have completed all steps in Method 2, refer to [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="72ec0-230">Ver también</span><span class="sxs-lookup"><span data-stu-id="72ec0-230">See also</span></span>

- [<span data-ttu-id="72ec0-231">Consolidación en la nube para Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="72ec0-231">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="72ec0-232">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="72ec0-232">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)
