---
title: Implementar clientes para Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de clientes empresariales para Skype empresarial.'
ms.openlocfilehash: f40a4948deb495998debd033f449d9439fd8329b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234134"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="d73f6-103">Implementar clientes para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73f6-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="d73f6-104">**Resumen:** Información general sobre los métodos de instalación de clientes empresariales para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d73f6-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="d73f6-105">La forma de implementar Skype empresarial para sus usuarios depende de si compró Skype empresarial como parte de un plan de Office 365 o si compró una versión de licencia por volumen de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d73f6-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="d73f6-106">**Office 365** Si tiene un plan 365 de Office que incluye Skype empresarial, la tecnología de instalación que se usa se denomina hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d73f6-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="d73f6-107">Con Office 365, puede permitir que los usuarios instalen Skype empresarial por sí mismos desde el portal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d73f6-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="d73f6-108">O bien, puede implementar Skype empresarial para sus usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d73f6-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="d73f6-109">Para obtener información sobre la instalación de Skype empresarial que se incluye con Office 365, consulte [implementar el cliente de Skype empresarial en office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="d73f6-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="d73f6-110">**Licencias por volumen** Si tiene una versión de licencia por volumen del cliente de Skype empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="d73f6-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="d73f6-111">Un paquete de instalación basado en Windows Installer consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="d73f6-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="d73f6-112">Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo.</span><span class="sxs-lookup"><span data-stu-id="d73f6-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="d73f6-113">La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d73f6-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="d73f6-114">El cliente de Skype empresarial 2019 usa instaladores de hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d73f6-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="d73f6-115">En los temas de esta sección se describe cómo usar y personalizar Windows Installer para implementar el cliente de Skype empresarial a los usuarios a través de los procedimientos normales.</span><span class="sxs-lookup"><span data-stu-id="d73f6-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d73f6-116">El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con los clientes de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d73f6-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d73f6-117">El programa de instalación de Office 365 no desinstala versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="d73f6-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="d73f6-118">El cliente de Skype empresarial se instala en paralelo con otros clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="d73f6-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="d73f6-119">Instalación de clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="d73f6-119">Installing Windows clients</span></span>

- [<span data-ttu-id="d73f6-120">Personalizar la instalación del cliente de Windows en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73f6-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="d73f6-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d73f6-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="d73f6-122">Configurar la lista de contactos inteligentes en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73f6-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="d73f6-123">Instalar clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d73f6-123">Installing device clients</span></span>

- [<span data-ttu-id="d73f6-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d73f6-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="d73f6-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="d73f6-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="d73f6-126">Implementar el complemento VDI para Lync con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73f6-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="d73f6-127">Implementar clientes descargables en Internet en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73f6-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="d73f6-128">Personalizar la experiencia del cliente de Mac en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="d73f6-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="d73f6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d73f6-129">See also</span></span>

[<span data-ttu-id="d73f6-130">Implementar el cliente de Skype empresarial en Office 365</span><span class="sxs-lookup"><span data-stu-id="d73f6-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
