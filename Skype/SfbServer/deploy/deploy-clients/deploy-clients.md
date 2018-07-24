---
title: Implementar a clientes de Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.'
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985690"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="aec5c-103">Implementar a clientes de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="aec5c-104">**Resumen:** Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="aec5c-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="aec5c-105">Cómo implementar Skype para la empresa a los usuarios depende de si ha comprado Skype para la empresa como parte de un plan de Office 365 o ha comprado una versión con licencia por volumen de Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="aec5c-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="aec5c-106">**Office 365** Si dispone de un plan de Office 365 que incluya Skype para la empresa, la tecnología de instalación que se utiliza se denomina Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="aec5c-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="aec5c-107">Con Office 365, puede permitir a los usuarios instalar Skype para la empresa para sí mismos desde el portal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="aec5c-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="aec5c-108">O bien, puede implementar Skype para la empresa a los usuarios descargar el software en su red local y, a continuación, usando las herramientas de implementación de software existente, como con Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aec5c-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="aec5c-109">Para obtener información de instalación acerca de Skype para la empresa que se incluye con Office 365, vea [implementar el Skype para cliente empresarial en Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="aec5c-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="aec5c-110">**Con licencia por volumen** Si tiene una versión con licencia de volumen de la Skype para 2015 empresarial o el cliente de 2016, la tecnología de instalación que se utiliza es Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="aec5c-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="aec5c-111">Un paquete de instalación basada en Windows Installer consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="aec5c-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="aec5c-112">Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo.</span><span class="sxs-lookup"><span data-stu-id="aec5c-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="aec5c-113">La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="aec5c-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="aec5c-114">El Skype para cliente empresarial 2019 usa a instaladores de Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="aec5c-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="aec5c-115">En los temas de esta sección se describen cómo utilizar y personalizar Windows Installer para implementar la Skype para cliente de negocio para los usuarios a través de los procedimientos de normales.</span><span class="sxs-lookup"><span data-stu-id="aec5c-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aec5c-116">El complemento de Skype Meeting para Microsoft Office, que admite la administración de la reunión desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="aec5c-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aec5c-117">El programa de instalación de Office 365 no desinstala las versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="aec5c-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="aec5c-118">El Skype para clientes empresariales instala en paralelo con otros clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="aec5c-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="aec5c-119">Instalación de los clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="aec5c-119">Installing Windows clients</span></span>

- [<span data-ttu-id="aec5c-120">Personalizar la instalación de cliente de Windows en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="aec5c-121">Configurar la experiencia del cliente con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aec5c-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="aec5c-122">Configurar la lista de contactos inteligentes en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="aec5c-123">Instalación de los clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="aec5c-123">Installing device clients</span></span>

- [<span data-ttu-id="aec5c-124">Skype Empresarial Server 2015: instalar y probar Skype Empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="aec5c-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="aec5c-125">Instalar y probar Skype Empresarial para iOS</span><span class="sxs-lookup"><span data-stu-id="aec5c-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="aec5c-126">Implementar el Sistema de salas de Skype en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="aec5c-127">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="aec5c-127">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="aec5c-128">Implementación del complemento Lync VDI con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="aec5c-129">Implementar a los clientes que se pueden descargar de Web en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="aec5c-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="aec5c-130">Personalizar la experiencia del cliente de Mac en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aec5c-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="aec5c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec5c-131">See also</span></span>

[<span data-ttu-id="aec5c-132">Implementar el Skype para cliente empresarial en Office 365</span><span class="sxs-lookup"><span data-stu-id="aec5c-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)