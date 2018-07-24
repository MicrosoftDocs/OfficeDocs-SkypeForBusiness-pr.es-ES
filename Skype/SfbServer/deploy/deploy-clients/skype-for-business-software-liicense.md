---
title: Skype de Skype salón del sistema de licencia de software de negocio
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: ba582174483eb511387ae085aba97d02631665fc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965425"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="ff4a0-103">Sistema de salas de Skype: licencia del software de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ff4a0-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="ff4a0-104">Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="ff4a0-105">Sistema de sala de Skype usa un Skype instalado para cliente de negocio, que requiere una licencia de volumen de software.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="ff4a0-106">Antes de implementar el primer sistema de sala de Skype, averiguar el estado de licencia por volumen de la implementación - mediante los servidores de administración de claves (KMS) o las claves de activación múltiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="ff4a0-107">Servidores de administración de claves (KMS)</span><span class="sxs-lookup"><span data-stu-id="ff4a0-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="ff4a0-108">Si KMS se encuentran disponibles y distribuirá Skype para las activaciones de licencias por volumen de negocio, el sistema de sala de Skype se activará automáticamente el Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="ff4a0-109">Para averiguar si está configurado el KMS realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4a0-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="ff4a0-110">Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="ff4a0-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="ff4a0-111">Para obtener más información, vea [cómo detectar hosts de KMS de Windows y de Office a través de DNS y quitar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="ff4a0-112">Para configurar un KMS, vea [activación de KMS de Office 2013](https://technet.microsoft.com/library/ee624357.aspx) y [Gvlk para la activación de KMS y Active Directory de Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff4a0-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="ff4a0-113">Clave de licencia de volumen Office 2013 genérico de Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de sala de Skype buscar un KMS en la red).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="ff4a0-114">Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)</span><span class="sxs-lookup"><span data-stu-id="ff4a0-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="ff4a0-115">Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="ff4a0-116">También Esto permitirá que la compañía compra de Skype para las activaciones de negocio VL, después de que la empresa puede obtener una clave de MAK para la entrada de la consola de administración del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="ff4a0-117">Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="ff4a0-118">Si no sabe con seguridad, departamento de finanzas del cliente debe ser capaz de confirmar si el cliente ha pagado un VLA.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="ff4a0-119">Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="ff4a0-120">Para obtener más información, vaya al [Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="ff4a0-121">MAK para Office 365 sin acceso al VLSC</span><span class="sxs-lookup"><span data-stu-id="ff4a0-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="ff4a0-122">Si el cliente no tiene un contrato de licencia por volumen, Skype para las activaciones de negocio será mucho más difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="ff4a0-123">Sin embargo, los clientes de Office 365 sin acceso VLSC pueden obtener una MAK promocional proporcionando la siguiente información a los OEM vender el sistema de sala de Skype:</span><span class="sxs-lookup"><span data-stu-id="ff4a0-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="ff4a0-124">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="ff4a0-124">Company name</span></span>
    
- <span data-ttu-id="ff4a0-125">Nombre de contacto, correo electrónico y número de teléfono de la implementación</span><span class="sxs-lookup"><span data-stu-id="ff4a0-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="ff4a0-126">Número de sistemas de implementada</span><span class="sxs-lookup"><span data-stu-id="ff4a0-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="ff4a0-127">Fecha de implementación</span><span class="sxs-lookup"><span data-stu-id="ff4a0-127">Deployment date</span></span>
    
- <span data-ttu-id="ff4a0-128">Si el cliente tiene un administrador de cuentas de técnicos de Microsoft, el TAM nombre e información de contacto</span><span class="sxs-lookup"><span data-stu-id="ff4a0-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

