---
title: Implementar la herramienta SEFAUtil en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantación de la herramienta SEFAUtil en Skype para Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="8ceca-103">Implementar la herramienta SEFAUtil en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="8ceca-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="8ceca-104">Implantación de la herramienta SEFAUtil en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ceca-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="8ceca-105">Para implementar y administrar grupo llamar recogida, necesitará utilizar el Skype para la versión de la herramienta SEFAUtil Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ceca-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8ceca-106">Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="8ceca-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="8ceca-107">Puede ejecutar la herramienta SEFAUtil en cualquier grupo de Front-End de su implementación.</span><span class="sxs-lookup"><span data-stu-id="8ceca-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ceca-108">Para obtener más información acerca de cómo ejecutar SEFAUtil, consulte el artículo del blog de Technet "[cómo obtener SEFAutil ejecutando?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="8ceca-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="8ceca-109">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="8ceca-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="8ceca-110">Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="8ceca-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8ceca-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8ceca-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8ceca-112">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ceca-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="8ceca-113">Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de Front-End donde piensa ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="8ceca-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="8ceca-114">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8ceca-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="8ceca-p102">Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8ceca-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="8ceca-117">Si es preciso, puede usar otro puerto.</span><span class="sxs-lookup"><span data-stu-id="8ceca-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="8ceca-p103">Habilite la topología con los cambios. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8ceca-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="8ceca-120">Si no lo ha hecho ya, descargar el Skype para la versión de la herramienta SEFAUtil Business Server desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instalar en el grupo de aplicaciones de confianza creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="8ceca-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="8ceca-121">Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:</span><span class="sxs-lookup"><span data-stu-id="8ceca-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="8ceca-122">a.</span><span class="sxs-lookup"><span data-stu-id="8ceca-122">a.</span></span> <span data-ttu-id="8ceca-123">Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="8ceca-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="8ceca-124">b.</span><span class="sxs-lookup"><span data-stu-id="8ceca-124">b.</span></span> <span data-ttu-id="8ceca-125">Muestre la configuración de reenvío de llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="8ceca-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="8ceca-126">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8ceca-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="8ceca-127">Aparecerá la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ceca-127">The call forwarding settings for the user will be displayed.</span></span>
    

