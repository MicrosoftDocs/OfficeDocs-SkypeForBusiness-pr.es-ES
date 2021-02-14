---
title: Implementar clientes para Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de clientes empresariales para Skype Empresarial.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805700"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="d8607-103">Implementar clientes para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8607-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="d8607-104">**Resumen:** Información general sobre los métodos de instalación de clientes empresariales para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8607-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="d8607-105">La forma de implementar Skype Empresarial para los usuarios depende de si compró Skype Empresarial como parte de un plan de Microsoft 365 u Office 365 o si compró una versión con licencia por volumen de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8607-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of a Microsoft 365 or Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="d8607-106">**Microsoft 365 u Office 365** Si tiene un plan de Microsoft 365 u Office 365 que incluya Skype Empresarial, la tecnología de instalación que se usa se denomina Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d8607-106">**Microsoft 365 or Office 365** If you have a Microsoft 365 or Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="d8607-107">Puede permitir que los usuarios instalen Skype Empresarial por sí mismos desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8607-107">You can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="d8607-108">O bien, puede implementar Skype Empresarial para sus usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d8607-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d8607-109">Para obtener información de instalación sobre Skype Empresarial que se incluye con Microsoft 365 y Office 365, vea Implementar el cliente de Skype Empresarial en [Microsoft 365 u Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="d8607-109">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="d8607-110">**Licencia por volumen** Si tiene una versión con licencia por volumen del cliente de Skype Empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="d8607-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="d8607-111">Un paquete de instalación basado en Windows Installer consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="d8607-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="d8607-112">Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo.</span><span class="sxs-lookup"><span data-stu-id="d8607-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="d8607-113">La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8607-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="d8607-114">El cliente de Skype Empresarial 2019 usa instaladores de Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d8607-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="d8607-115">Los temas de esta sección describen cómo usar y personalizar Windows Installer para implementar el cliente de Skype Empresarial para los usuarios a través de sus procedimientos normales.</span><span class="sxs-lookup"><span data-stu-id="d8607-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8607-116">El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con clientes de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8607-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d8607-117">Los programas de instalación de Microsoft 365 y Office 365 no desinstalan versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="d8607-117">The Microsoft 365 and Office 365 setup programs don't uninstall previous versions of Lync.</span></span> <span data-ttu-id="d8607-118">El cliente de Skype Empresarial se instala en paralelo con otros clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="d8607-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="d8607-119">Instalación de clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="d8607-119">Installing Windows clients</span></span>

- [<span data-ttu-id="d8607-120">Personalizar la instalación de cliente de Windows en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8607-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="d8607-121">Configurar la experiencia del cliente con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="d8607-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="d8607-122">Configurar la lista de contactos inteligentes en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8607-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="d8607-123">Instalación de clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d8607-123">Installing device clients</span></span>

- [<span data-ttu-id="d8607-124">Instalar y probar Skype Empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d8607-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="d8607-125">Instalar y probar Skype Empresarial para iOS</span><span class="sxs-lookup"><span data-stu-id="d8607-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="d8607-126">Implementar el complemento Lync VDI con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8607-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="d8607-127">Implementar clientes web descargables en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8607-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="d8607-128">Personalizar la experiencia de cliente mac en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="d8607-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="d8607-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8607-129">See also</span></span>

[<span data-ttu-id="d8607-130">Implementar el cliente de Skype Empresarial en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d8607-130">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
