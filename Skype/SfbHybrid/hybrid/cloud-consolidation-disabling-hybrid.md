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
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120359"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="bbda2-103">Deshabilitar la migración híbrida para completar la migración a la nube: Información general</span><span class="sxs-lookup"><span data-stu-id="bbda2-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="bbda2-104">Después de mover todos los usuarios del entorno local a la nube, puede desactivar la implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bbda2-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="bbda2-105">Aparte de quitar cualquier hardware, un paso fundamental es separar lógicamente esa implementación local de Microsoft 365 u Office 365 deshabilitando la implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="bbda2-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="bbda2-106">Deshabilitar la implementación híbrida consta de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="bbda2-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="bbda2-107">Actualice los registros DNS para que apunten a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbda2-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="bbda2-108">Deshabilite el espacio de direcciones sip compartido (también conocido como "dominio dividido") en la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbda2-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="bbda2-109">Deshabilite la capacidad de comunicarse localmente con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbda2-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="bbda2-110">Estos pasos separan lógicamente la implementación local de Skype Empresarial Server de Office 365 y deben realizarse conjuntamente como una unidad.</span><span class="sxs-lookup"><span data-stu-id="bbda2-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="bbda2-111">Los detalles de cada paso se proporcionan en este artículo a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbda2-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="bbda2-112">Una vez completado, puede retirar la implementación local de Skype Empresarial mediante uno de los dos métodos a los que se hace referencia a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbda2-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="bbda2-113">Una vez completada esta separación lógica, los atributos msRTCSIP de su Active Directory local siguen teniendo valores y seguirán sincroniciendo a través de Azure AD Connect en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbda2-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="bbda2-114">La forma de retirar el entorno local depende de si desea dejar estos atributos en su lugar o, en primer lugar, borrarlos de su Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="bbda2-115">Tenga en cuenta que borrar los atributos msRTCSIP locales después de migrar desde local podría provocar la pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="bbda2-116">A continuación se describen los detalles y las disociones de los dos métodos de retirada.</span><span class="sxs-lookup"><span data-stu-id="bbda2-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="bbda2-117">Deshabilitar híbrido para completar la migración a la nube: Pasos detallados</span><span class="sxs-lookup"><span data-stu-id="bbda2-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="bbda2-118">*Actualice DNS para que apunte a Microsoft 365 u Office 365.*</span><span class="sxs-lookup"><span data-stu-id="bbda2-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="bbda2-119">El DNS externo de la organización para la organización local debe actualizarse para que los registros de Skype Empresarial apunten a Microsoft 365 u Office 365 en lugar de a la implementación local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="bbda2-120">En particular:</span><span class="sxs-lookup"><span data-stu-id="bbda2-120">Specifically:</span></span>

    |<span data-ttu-id="bbda2-121">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="bbda2-121">Record type</span></span>|<span data-ttu-id="bbda2-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="bbda2-122">Name</span></span>|<span data-ttu-id="bbda2-123">TTL</span><span class="sxs-lookup"><span data-stu-id="bbda2-123">TTL</span></span>|<span data-ttu-id="bbda2-124">Valor</span><span class="sxs-lookup"><span data-stu-id="bbda2-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="bbda2-125">SRV</span><span class="sxs-lookup"><span data-stu-id="bbda2-125">SRV</span></span>|<span data-ttu-id="bbda2-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="bbda2-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="bbda2-127">3600</span><span class="sxs-lookup"><span data-stu-id="bbda2-127">3600</span></span>|<span data-ttu-id="bbda2-128">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="bbda2-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="bbda2-129">SRV</span><span class="sxs-lookup"><span data-stu-id="bbda2-129">SRV</span></span>|<span data-ttu-id="bbda2-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="bbda2-130">_sip._tls</span></span>|<span data-ttu-id="bbda2-131">3600</span><span class="sxs-lookup"><span data-stu-id="bbda2-131">3600</span></span>|<span data-ttu-id="bbda2-132">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="bbda2-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="bbda2-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="bbda2-133">CNAME</span></span>| <span data-ttu-id="bbda2-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bbda2-134">lyncdiscover</span></span>|   <span data-ttu-id="bbda2-135">3600</span><span class="sxs-lookup"><span data-stu-id="bbda2-135">3600</span></span>|   <span data-ttu-id="bbda2-136">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="bbda2-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="bbda2-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="bbda2-137">CNAME</span></span>| <span data-ttu-id="bbda2-138">sip</span><span class="sxs-lookup"><span data-stu-id="bbda2-138">sip</span></span>|    <span data-ttu-id="bbda2-139">3600</span><span class="sxs-lookup"><span data-stu-id="bbda2-139">3600</span></span>|   <span data-ttu-id="bbda2-140">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="bbda2-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="bbda2-141">Además, se pueden eliminar los registros CNAME para meet o dialin (si están presentes).</span><span class="sxs-lookup"><span data-stu-id="bbda2-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="bbda2-142">Por último, se deben quitar los registros DNS de Skype Empresarial en la red interna.</span><span class="sxs-lookup"><span data-stu-id="bbda2-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="bbda2-143">En raras ocasiones, cambiar DNS de apuntar localmente a Microsoft 365 u Office 365 para su organización puede provocar que la federación con otras organizaciones deje de funcionar hasta que otra organización actualice su configuración de federación:</span><span class="sxs-lookup"><span data-stu-id="bbda2-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="bbda2-144">Las organizaciones federadas que usan el modelo de federación directa anterior (también conocido como Servidor de partners permitidos) tendrán que actualizar las entradas de dominio permitidas para su organización para quitar el FQDN de proxy.</span><span class="sxs-lookup"><span data-stu-id="bbda2-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="bbda2-145">Este modelo de federación heredado no se basa en registros SRV de DNS, por lo que dicha configuración se desatendrán una vez que la organización se mueva a la nube.</span><span class="sxs-lookup"><span data-stu-id="bbda2-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="bbda2-146">Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync. <span> com tendrá que actualizar su configuración para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="bbda2-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="bbda2-147">Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea.</span><span class="sxs-lookup"><span data-stu-id="bbda2-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="bbda2-148">En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="bbda2-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="bbda2-149">Si sospecha que alguno de sus socios federados puede estar usando Direct Federation o no haber federado con ninguna organización híbrida o en línea, le sugerimos que envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.</span><span class="sxs-lookup"><span data-stu-id="bbda2-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="bbda2-150">*Deshabilite el espacio de direcciones sip compartido en la organización de Microsoft 365 u Office 365.*</span><span class="sxs-lookup"><span data-stu-id="bbda2-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="bbda2-151">El siguiente comando debe realizarse desde una ventana de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bbda2-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="bbda2-152">*Deshabilite la capacidad de comunicarse localmente con Microsoft 365 u Office 365.*</span><span class="sxs-lookup"><span data-stu-id="bbda2-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="bbda2-153">El siguiente comando debe realizarse desde una ventana de PowerShell local:</span><span class="sxs-lookup"><span data-stu-id="bbda2-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="bbda2-154">Administración de atributos después de mover usuarios de local a la nube</span><span class="sxs-lookup"><span data-stu-id="bbda2-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="bbda2-155">De forma predeterminada, todos los usuarios que se habilitaron anteriormente para Skype Empresarial Server y que posteriormente se movieron a la nube aún tienen atributos msRTCSIP configurados en active directory local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="bbda2-156">Estos atributos, en particular la dirección sip (msRTCSIP-PrimaryUserAddress) y el número de teléfono potencialmente (msRTCSIP-Line), siguen sincroniciendo en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbda2-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="bbda2-157">Si se requieren cambios en cualquiera de los atributos msRTCSIP, estos cambios deben realizarse en Active Directory local y, a continuación, sincronizarse con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbda2-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="bbda2-158">Sin embargo, una vez que se haya quitado la implementación de Skype Empresarial Server, las herramientas de Skype Empresarial Server no estarán disponibles para administrar estos atributos.</span><span class="sxs-lookup"><span data-stu-id="bbda2-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="bbda2-159">Hay dos opciones disponibles para controlar esta situación:</span><span class="sxs-lookup"><span data-stu-id="bbda2-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="bbda2-160">Deje los usuarios habilitados para cuentas de servidor de Skype Empresarial tal como están y administre los atributos msRTCSIP con herramientas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bbda2-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="bbda2-161">Esto garantiza que no se pierda el servicio para los usuarios migrados y le permite quitar fácilmente la implementación de Skype Empresarial Server eliminando (por ejemplo, limpiando) los servidores, sin un desmantelamiento completo.</span><span class="sxs-lookup"><span data-stu-id="bbda2-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="bbda2-162">Sin embargo, los usuarios recién con licencia no tendrán estos atributos rellenados en su Active Directory local y tendrán que administrarse en línea.</span><span class="sxs-lookup"><span data-stu-id="bbda2-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="bbda2-163">Borre todos los atributos msRTCSIP de los usuarios migrados en su Active Directory local y administre estos atributos con herramientas en línea.</span><span class="sxs-lookup"><span data-stu-id="bbda2-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="bbda2-164">Este método permite un enfoque de administración coherente para los usuarios existentes y nuevos, pero puede provocar una pérdida temporal del servicio durante el proceso de retirada local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="bbda2-165">Método 1: administrar direcciones sip y números de teléfono para usuarios de Active Directory</span><span class="sxs-lookup"><span data-stu-id="bbda2-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="bbda2-166">Los administradores pueden administrar usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube, incluso después de retirar la implementación local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="bbda2-167">Si desea realizar cambios en la dirección sip de un usuario o en el número de teléfono de un usuario (y la dirección sip o el número de teléfono ya tiene un valor en Active Directory local), debe hacerlo en Active Directory local y permitir que los valores fluyan hasta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbda2-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="bbda2-168">Esto NO requiere Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="bbda2-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="bbda2-169">En su lugar, puede modificar estos atributos directamente en Active Directory local, mediante el complemento MMC usuarios y equipos de Active Directory (como se muestra a continuación) o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbda2-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="bbda2-170">Si usa el complemento MMC, abra la página de propiedades del usuario, haga clic en la pestaña Editor de atributos y busque los atributos adecuados para modificar:</span><span class="sxs-lookup"><span data-stu-id="bbda2-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="bbda2-171">Para modificar la dirección sip de un usuario, modifique `msRTCSIP-PrimaryUserAddress` el archivo .</span><span class="sxs-lookup"><span data-stu-id="bbda2-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="bbda2-172">Tenga en cuenta que si el atributo contiene una dirección sip, actualice `ProxyAddresses` también ese valor como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="bbda2-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="bbda2-173">Aunque O365 omite la dirección sip si está rellenada, otros componentes locales pueden `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` usarla.</span><span class="sxs-lookup"><span data-stu-id="bbda2-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="bbda2-174">Para modificar el número de teléfono de un usuario, modifique `msRTCSIP-Line` *si ya tiene un valor*.</span><span class="sxs-lookup"><span data-stu-id="bbda2-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Herramienta de equipos y usuarios de Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="bbda2-176">Si el usuario no tenía originalmente un valor para local antes del movimiento, puede modificar el número de teléfono mediante el parámetro - en el `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) del módulo PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bbda2-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="bbda2-177">Estos pasos no son necesarios para los nuevos usuarios creados después de deshabilitar híbridos y esos usuarios se pueden administrar directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="bbda2-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="bbda2-178">Si se siente cómodo con la combinación de estos métodos, así como con dejar los atributos msRTCSIP en su Active Directory local, simplemente puede volver a crear una imagen de los servidores locales de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bbda2-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="bbda2-179">Sin embargo, si prefiere borrar todos los atributos msRTCSIP y realizar una desinstalación tradicional de Skype Empresarial Server, use el método 2.</span><span class="sxs-lookup"><span data-stu-id="bbda2-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="bbda2-180">Método 2: Borrar atributos de Skype Empresarial para todos los usuarios locales de Active Directory</span><span class="sxs-lookup"><span data-stu-id="bbda2-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="bbda2-181">Esta opción requiere un esfuerzo adicional y una planeación adecuada, ya que los usuarios que se movieron anteriormente de un Skype Empresarial Server local a la nube deben volver a aprovisionarse.</span><span class="sxs-lookup"><span data-stu-id="bbda2-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="bbda2-182">Estos usuarios se pueden clasificar en dos categorías diferentes: usuarios sin sistema telefónico y usuarios con sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bbda2-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="bbda2-183">Los usuarios con sistema telefónico experimentarán una pérdida temporal del servicio telefónico como parte de la transición del número de teléfono desde que se administra en Active Directory local a la nube.</span><span class="sxs-lookup"><span data-stu-id="bbda2-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="bbda2-184">**Se recomienda realizar un piloto en el que participen un número reducido de usuarios con sistema telefónico antes de iniciar operaciones masivas de usuario.**</span><span class="sxs-lookup"><span data-stu-id="bbda2-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="bbda2-185">Para implementaciones grandes, los usuarios pueden procesarse en grupos más pequeños en diferentes ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbda2-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="bbda2-186">El proceso es más sencillo para los usuarios que tienen una dirección sip correspondiente y UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="bbda2-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="bbda2-187">Para las organizaciones que tienen usuarios con valores que no coinciden en estos dos atributos, se debe tener cuidado adicional como se indica a continuación para una transición sin problemas.</span><span class="sxs-lookup"><span data-stu-id="bbda2-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="bbda2-188">Confirme que el siguiente cmdlet local de PowerShell de Skype Empresarial devuelve un resultado vacío.</span><span class="sxs-lookup"><span data-stu-id="bbda2-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="bbda2-189">Un resultado vacío significa que ningún usuario está internamente y se ha movido a Office 365 o se ha deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="bbda2-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="bbda2-190">Registre el número de teléfono actual de los usuarios (LineUri), UserPrincipalName e información relacionada, ejecutando el siguiente cmdlet local de PowerShell de Skype Empresarial Server para exportar datos de usuario:</span><span class="sxs-lookup"><span data-stu-id="bbda2-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="bbda2-191">Antes de continuar, abra SfbUserSettings.csv archivo y confirme que todos los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbda2-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="bbda2-192">Se recomienda conservar una copia de este archivo.</span><span class="sxs-lookup"><span data-stu-id="bbda2-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="bbda2-193">No use este archivo en los siguientes pasos para procesar usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="bbda2-194">Cree un archivo con un grupo de usuarios que se usará en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="bbda2-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="bbda2-195">Después de que el primer grupo de usuarios se haya completado correctamente, continúe con el siguiente grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="bbda2-196">En el ejemplo siguiente, los grupos de usuarios se seleccionan alfabéticamente, pero puede filtrar por usuarios en función de criterios que coincidan con la forma en que desea procesar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="bbda2-197">Antes de continuar, abra SfbUsers.csv archivo y confirme que los datos de usuario se han exportado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbda2-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="bbda2-198">Necesitará LineUri (número de teléfono), UserPrincipalName, SamAccountName y SipAddress de este archivo en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="bbda2-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="bbda2-199">Elimine la información de atributo relacionada con Skype Empresarial Server de Active Directory para el conjunto de usuarios que está listo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="bbda2-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="bbda2-200">Hay dos pasos para este proceso, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbda2-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="bbda2-201">Después del siguiente ciclo de sincronización de AAD después de ejecutar este paso, los usuarios con sistema telefónico que se movieron previamente de un Skype Empresarial Server local a la nube perderán la capacidad de realizar y recibir llamadas hasta que el paso 8 se complete correctamente y se confirme en el paso 9.</span><span class="sxs-lookup"><span data-stu-id="bbda2-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="bbda2-202">Además, asegúrese de haber guardado los números de teléfono del usuario y la información relacionada según el paso 2, ya que esa información es necesaria para ese paso.</span><span class="sxs-lookup"><span data-stu-id="bbda2-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="bbda2-203">A continuación, para el mismo conjunto de usuarios, desactive el valor de msRTCSIP-DeploymentLocator con PowerShell de Active Directory local:</span><span class="sxs-lookup"><span data-stu-id="bbda2-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="bbda2-204">Ejecute el siguiente cmdlet local de PowerShell de Skype Empresarial para agregar el valor de la dirección sip al proxy de Active Directory localAddresses.</span><span class="sxs-lookup"><span data-stu-id="bbda2-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="bbda2-205">Esto evitará problemas de interoperabilidad que dependen de este atributo.</span><span class="sxs-lookup"><span data-stu-id="bbda2-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="bbda2-206">Ejecutar Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="bbda2-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="bbda2-207">Espere a que se complete el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="bbda2-208">Puede supervisar el progreso del aprovisionamiento de usuarios ejecutando el siguiente comando de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bbda2-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="bbda2-209">El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="bbda2-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="bbda2-210">Ejecute el siguiente comando de PowerShell de Skype Empresarial Online para asignar números de teléfono y habilitar a los usuarios para el sistema telefónico:</span><span class="sxs-lookup"><span data-stu-id="bbda2-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="bbda2-211">Si todavía tiene puntos de conexión de Skype Empresarial (ya sea clientes de Skype o teléfonos de terceros), también querrá establecer -HostedVoiceMail en $true.</span><span class="sxs-lookup"><span data-stu-id="bbda2-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="bbda2-212">Si su organización solo usa puntos de conexión de Teams para usuarios habilitados para voz, esta configuración no se aplica a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="bbda2-213">Confirme que los usuarios con funcionalidad del sistema telefónico se han aprovisionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbda2-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="bbda2-214">El siguiente comando de PowerShell de Skype Empresarial Online devuelve un resultado vacío en cuanto se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="bbda2-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="bbda2-215">Repita los pasos del 3 al 9 hasta que se procese a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbda2-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="bbda2-216">Confirme que todos los usuarios se han procesado correctamente ejecutando los dos comandos de PowerShell siguientes.</span><span class="sxs-lookup"><span data-stu-id="bbda2-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="bbda2-217">Comando de PowerShell local de Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="bbda2-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="bbda2-218">Comando de PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="bbda2-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="bbda2-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbda2-219">See also</span></span>

[<span data-ttu-id="bbda2-220">Consolidación en la nube para Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bbda2-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)