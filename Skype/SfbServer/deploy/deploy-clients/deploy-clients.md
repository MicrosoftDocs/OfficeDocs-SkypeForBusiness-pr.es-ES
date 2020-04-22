---
title: Implementación de clientes de Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de cliente empresarial para Skype empresarial.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778286"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="1615c-103">Implementación de clientes de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1615c-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="1615c-104">**Resumen:** Información general sobre los métodos de instalación de cliente empresarial para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1615c-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="1615c-105">La forma en que se implementa Skype empresarial para los usuarios depende de si compró Skype empresarial como parte de un plan de Office 365 o si adquirió una versión de licencia por volumen de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1615c-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="1615c-106">**Office 365** Si tiene un plan de Office 365 que incluye Skype empresarial, la tecnología de instalación que se usa se llama hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1615c-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="1615c-107">Con Office 365, puede permitir que los usuarios instalen Skype empresarial para sí mismos desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1615c-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1615c-108">O bien, puede implementar Skype empresarial para los usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1615c-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1615c-109">Para obtener información sobre la instalación de Skype empresarial que se incluye con Office 365, consulte [implementar el cliente de Skype empresarial en office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="1615c-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="1615c-110">**Licencia por volumen** Si tiene una versión de licencia por volumen del cliente de Skype empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="1615c-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="1615c-111">Un paquete de instalación basado en Windows Installer consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="1615c-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="1615c-112">Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo.</span><span class="sxs-lookup"><span data-stu-id="1615c-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="1615c-113">La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1615c-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="1615c-114">El cliente de Skype empresarial 2019 usa instaladores de hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1615c-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="1615c-115">En los temas de esta sección se describe cómo usar y personalizar Windows Installer para implementar el cliente de Skype empresarial para los usuarios a través de los procedimientos normales.</span><span class="sxs-lookup"><span data-stu-id="1615c-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1615c-116">El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con los clientes de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1615c-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1615c-117">El programa de instalación de Office 365 no desinstala versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="1615c-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="1615c-118">El cliente de Skype empresarial se instala en paralelo con otros clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="1615c-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="1615c-119">Instalación de clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="1615c-119">Installing Windows clients</span></span>

- [<span data-ttu-id="1615c-120">Personalización de la instalación del cliente de Windows en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1615c-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="1615c-121">Configurar la experiencia de cliente con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1615c-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="1615c-122">Configurar la lista de contactos inteligentes en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1615c-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="1615c-123">Instalación de clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1615c-123">Installing device clients</span></span>

- [<span data-ttu-id="1615c-124">Instalar y probar Skype empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1615c-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="1615c-125">Instalar y probar Skype empresarial para iOS</span><span class="sxs-lookup"><span data-stu-id="1615c-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="1615c-126">Implementar el complemento Lync VDI con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1615c-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="1615c-127">Implementar clientes Web descargables en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1615c-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="1615c-128">Personalización de la experiencia del cliente Mac en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1615c-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="1615c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1615c-129">See also</span></span>

[<span data-ttu-id="1615c-130">Implementar el cliente de Skype empresarial en Office 365</span><span class="sxs-lookup"><span data-stu-id="1615c-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
