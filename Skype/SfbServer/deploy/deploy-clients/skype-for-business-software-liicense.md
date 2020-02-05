---
title: Licencia del software de Skype empresarial para sistemas de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768483"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="7a96f-103">Sistema de salas de Skype: licencia del software de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="7a96f-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="7a96f-104">Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a96f-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="7a96f-105">El sistema de salas de Skype usa un cliente de Skype para empresas instalado, que requiere una licencia por volumen de software.</span><span class="sxs-lookup"><span data-stu-id="7a96f-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="7a96f-106">Antes de implementar el primer sistema de la sala de Skype, averigüe el estado de la licencia por volumen de la implementación: con los servidores de administración de claves (KMS) o las claves de activación múltiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="7a96f-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="7a96f-107">Servidores de administración de claves (KMS)</span><span class="sxs-lookup"><span data-stu-id="7a96f-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="7a96f-108">Si KMS está en el lugar y va a distribuir las activaciones de licencias por volumen de Skype empresarial, el sistema de salas de Skype activará automáticamente el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a96f-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="7a96f-109">Para averiguar si está configurado el KMS realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a96f-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="7a96f-110">Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="7a96f-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="7a96f-111">Para obtener más información, consulte [Cómo descubrir los hosts de kms de Office y Windows a través de DNS y quitar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a96f-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="7a96f-112">Para configurar un KMS, consulte [activación de kms de office 2013](https://technet.microsoft.com/library/ee624357.aspx) y [GVLKs para kms y activación de active directory de Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="7a96f-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="7a96f-113">Clave de licencia por volumen genérica de Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de la sala de Skype busque un KMS en la red).</span><span class="sxs-lookup"><span data-stu-id="7a96f-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="7a96f-114">Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)</span><span class="sxs-lookup"><span data-stu-id="7a96f-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="7a96f-115">Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC.</span><span class="sxs-lookup"><span data-stu-id="7a96f-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="7a96f-116">Esto también permitirá a la empresa comprar activaciones VL de Skype empresarial, después de las cuales la empresa puede obtener una MAK para la entrada en la consola de administración de sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="7a96f-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="7a96f-117">Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK.</span><span class="sxs-lookup"><span data-stu-id="7a96f-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="7a96f-118">Si no está seguro, el Departamento de finanzas del cliente debe poder confirmar si el cliente ha recibido un VLA.</span><span class="sxs-lookup"><span data-stu-id="7a96f-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="7a96f-119">Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK).</span><span class="sxs-lookup"><span data-stu-id="7a96f-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="7a96f-120">Para obtener más información, vaya al [centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a96f-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="7a96f-121">MAK para Office 365 sin acceso al VLSC</span><span class="sxs-lookup"><span data-stu-id="7a96f-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="7a96f-122">Si el cliente no tiene un contrato de licencia por volumen, las activaciones de Skype para empresas serán mucho más difíciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="7a96f-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="7a96f-123">Sin embargo, los clientes de Office 365 sin acceso VLSC pueden obtener una MAK de promoción proporcionando la siguiente información al OEM vendiendo el sistema de salas de Skype:</span><span class="sxs-lookup"><span data-stu-id="7a96f-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="7a96f-124">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="7a96f-124">Company name</span></span>
    
- <span data-ttu-id="7a96f-125">Nombre de contacto, correo electrónico y número de teléfono de la implementación</span><span class="sxs-lookup"><span data-stu-id="7a96f-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="7a96f-126">Número de sistemas implementados</span><span class="sxs-lookup"><span data-stu-id="7a96f-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="7a96f-127">Fecha de implementación</span><span class="sxs-lookup"><span data-stu-id="7a96f-127">Deployment date</span></span>
    
- <span data-ttu-id="7a96f-128">Si el cliente tiene un administrador de cuentas técnico de Microsoft, el nombre y la información de contacto del TAM</span><span class="sxs-lookup"><span data-stu-id="7a96f-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

