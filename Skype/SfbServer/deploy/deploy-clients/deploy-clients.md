---
title: Implementar clientes para Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: Resumen de métodos de instalación de cliente de empresa de Skype para el negocio.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="86fe9-103">Implementar clientes para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="86fe9-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86fe9-104">**Resumen:** Resumen de métodos de instalación de cliente de empresa de Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="86fe9-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="86fe9-105">Cómo implementar Skype para el negocio a los usuarios depende de si ha adquirido Skype para el negocio como parte de un plan de Office 365 o adquirir una versión con licencia de volumen de Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="86fe9-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="86fe9-106">**Office 365** Si tienes un plan de Office 365 que incluye Skype para el negocio, la tecnología de instalación que se utiliza se llama hacer clic para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="86fe9-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="86fe9-107">Con Office 365, puede permitir a los usuarios instalar Skype para el negocio por sí mismos desde el portal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="86fe9-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="86fe9-108">O bien, puede implementar Skype para el negocio a los usuarios descargar el software en la red local y utilizando las herramientas de despliegue de software existente, como con Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="86fe9-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="86fe9-109">Para obtener información de instalación acerca de Skype para el negocio que viene con Office 365, vea [implementar el Skype para cliente de negocio de Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="86fe9-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="86fe9-110">**Con licencia por volumen** Si tiene una versión de licencia por volumen de Skype para el negocio, la tecnología de instalación que se utiliza es Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="86fe9-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="86fe9-111">Un paquete de instalación basada en Windows Installer consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="86fe9-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="86fe9-112">Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo.</span><span class="sxs-lookup"><span data-stu-id="86fe9-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="86fe9-113">La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="86fe9-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="86fe9-114">En los temas de esta sección describen cómo utilizar y personalizar Windows Installer para implementar el Skype para cliente de negocio a los usuarios a través de los procedimientos normales.</span><span class="sxs-lookup"><span data-stu-id="86fe9-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86fe9-115">La reunión complemento de Skype para el negocio, el cliente de mensajería y colaboración, que admite reunión administración desde dentro de Outlook instala automáticamente con Skype para el negocio en línea.</span><span class="sxs-lookup"><span data-stu-id="86fe9-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="86fe9-116">El programa de instalación de Office 365 desinstalar versiones anteriores de Lync o Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="86fe9-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="86fe9-117">El Skype para Business client instala side-by-side con otros clientes de Office Communicator o de Lync.</span><span class="sxs-lookup"><span data-stu-id="86fe9-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="86fe9-118">Instalar los clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="86fe9-118">Installing Windows clients</span></span>

- [<span data-ttu-id="86fe9-119">Personalizar la instalación de cliente de Windows en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="86fe9-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="86fe9-120">Configurar la experiencia del cliente con Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="86fe9-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="86fe9-121">Configurar la lista de contactos inteligente de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="86fe9-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="86fe9-122">Instalar clientes de dispositivo</span><span class="sxs-lookup"><span data-stu-id="86fe9-122">Installing device clients</span></span>

- [<span data-ttu-id="86fe9-123">Instalar y probar Skype para negocios para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="86fe9-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="86fe9-124">Instalar y probar Skype para empresas para iOS</span><span class="sxs-lookup"><span data-stu-id="86fe9-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="86fe9-125">Implementar sistema de sala de Skype en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="86fe9-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="86fe9-126">Implementar sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="86fe9-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="86fe9-127">Implementar la VDI Lync complemento con Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="86fe9-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="86fe9-128">Implementar a clientes de Web descargables en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="86fe9-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="86fe9-129">Personalizar la experiencia del cliente de Mac en Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="86fe9-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="86fe9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="86fe9-130">See also</span></span>

#### 

[<span data-ttu-id="86fe9-131">Implementar el Skype para el cliente de negocio para su organización</span><span class="sxs-lookup"><span data-stu-id="86fe9-131">Deploy the Skype for Business client for your organization</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

