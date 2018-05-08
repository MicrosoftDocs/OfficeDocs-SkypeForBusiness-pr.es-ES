---
title: Implementar la herramienta SEFAUtil en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implementación de la herramienta de SEFAUtil de Skype para Business Server.
ms.openlocfilehash: f0bb660218b761e513e120f4ea5786eb9278b12a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="94973-103">Implementar la herramienta SEFAUtil en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="94973-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="94973-104">Implementación de la herramienta de SEFAUtil de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="94973-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="94973-105">Para implementar y administrar recogida de llamadas de grupo, debe usar el Skype para la versión de la herramienta SEFAUtil Business Server.</span><span class="sxs-lookup"><span data-stu-id="94973-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="94973-106">Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="94973-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="94973-107">Puede ejecutar la herramienta de SEFAUtil de cualquier grupo de servidores Front-End en su implementación.</span><span class="sxs-lookup"><span data-stu-id="94973-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94973-108">Para obtener más información acerca de cómo ejecutar SEFAUtil, vea el artículo del blog de Technet, "[cómo obtener SEFAutil ejecutando?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="94973-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="94973-109">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="94973-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="94973-110">Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.</span><span class="sxs-lookup"><span data-stu-id="94973-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="94973-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="94973-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="94973-112">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="94973-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="94973-113">Si es necesario, definir un grupo de servidores de aplicaciones de confianza para el grupo de servidores Front-End donde va a ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="94973-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="94973-114">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="94973-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="94973-p102">Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="94973-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="94973-117">Si es preciso, puede usar otro puerto.</span><span class="sxs-lookup"><span data-stu-id="94973-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="94973-p103">Habilite la topología con los cambios. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="94973-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="94973-120">Si no lo ha hecho ya, descargue el Skype para la versión de la herramienta SEFAUtil Business Server desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale en el grupo de aplicaciones de confianza que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="94973-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="94973-121">Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:</span><span class="sxs-lookup"><span data-stu-id="94973-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="94973-122">a.</span><span class="sxs-lookup"><span data-stu-id="94973-122">a.</span></span> <span data-ttu-id="94973-123">Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="94973-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="94973-124">b.</span><span class="sxs-lookup"><span data-stu-id="94973-124">b.</span></span> <span data-ttu-id="94973-125">Muestre la configuración de reenvío de llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="94973-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="94973-126">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="94973-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="94973-127">Aparecerá la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="94973-127">The call forwarding settings for the user will be displayed.</span></span>
    

