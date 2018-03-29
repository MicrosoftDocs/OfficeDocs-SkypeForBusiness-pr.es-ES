---
title: Skype de Skype sala sistema de licencia de software de negocios
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="7baad-103">Sistema de salas de Skype: licencia del software de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="7baad-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="7baad-104">Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="7baad-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="7baad-105">Sistema de sala de Skype utiliza un Skype instalado para cliente de negocio, que requiere una licencia de volumen de software.</span><span class="sxs-lookup"><span data-stu-id="7baad-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="7baad-106">Antes de implementar el primer sistema de sala de Skype, averigüe el estado de la licencia de volumen de la implementación - mediante servidores de administración de claves (KMS) o claves de activación múltiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="7baad-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="7baad-107">Servidores de administración de claves (KMS)</span><span class="sxs-lookup"><span data-stu-id="7baad-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="7baad-108">Si KMS están vigentes y distribuirá Skype para las activaciones de licencia de volumen de negocio, el sistema de sala de Skype se activará automáticamente el Skype para cliente de empresa.</span><span class="sxs-lookup"><span data-stu-id="7baad-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="7baad-109">Para averiguar si está configurado el KMS realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7baad-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="7baad-110">Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="7baad-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="7baad-111">Para obtener más información, vea [cómo descubrir hosts de KMS de Windows y de Office mediante DNS y eliminar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="7baad-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="7baad-112">Para configurar un KMS, consulte [activación de KMS de Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) y [GVLKs para la activación de KMS y Active Directory de Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="7baad-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="7baad-113">Clave de licencia de volumen Office 2013 genérico para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de sala de Skype para que busque un KMS en la red).</span><span class="sxs-lookup"><span data-stu-id="7baad-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="7baad-114">Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)</span><span class="sxs-lookup"><span data-stu-id="7baad-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="7baad-115">Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC.</span><span class="sxs-lookup"><span data-stu-id="7baad-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="7baad-116">Esto también permitirá a la empresa adquirir Skype para activaciones de negocio VL, después de que la empresa puede obtener una MAK para la entrada de la consola de administración del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="7baad-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="7baad-117">Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK.</span><span class="sxs-lookup"><span data-stu-id="7baad-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="7baad-118">Si no está seguro, departamento de finanzas del cliente debe ser capaz de confirmar si el cliente ha pagado por un VLA.</span><span class="sxs-lookup"><span data-stu-id="7baad-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="7baad-119">Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK).</span><span class="sxs-lookup"><span data-stu-id="7baad-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="7baad-120">Para obtener más información, vaya al [Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="7baad-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="7baad-121">MAK para Office 365 sin acceso al VLSC</span><span class="sxs-lookup"><span data-stu-id="7baad-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="7baad-122">Si el cliente no tiene un contrato de licencia de volumen, Skype para las activaciones de negocio será mucho más difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="7baad-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="7baad-123">Sin embargo, Office 365 sin acceso VLSC pueden obtener los clientes una MAK promocional proporcionando la siguiente información al OEM vendiendo el sistema de sala de Skype:</span><span class="sxs-lookup"><span data-stu-id="7baad-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="7baad-124">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="7baad-124">Company name</span></span>
    
- <span data-ttu-id="7baad-125">Nombre de contacto, correo electrónico y número de teléfono de la implementación</span><span class="sxs-lookup"><span data-stu-id="7baad-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="7baad-126">Número de sistemas implementados</span><span class="sxs-lookup"><span data-stu-id="7baad-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="7baad-127">Fecha de implementación</span><span class="sxs-lookup"><span data-stu-id="7baad-127">Deployment date</span></span>
    
- <span data-ttu-id="7baad-128">Si el cliente tiene Microsoft administrador técnico de cuentas, el TAM nombre e información de contacto</span><span class="sxs-lookup"><span data-stu-id="7baad-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

