---
title: Implementar la herramienta SEFAUtil en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implementación de la herramienta de SEFAUtil de Skype para Business Server.
ms.openlocfilehash: fc8b26dbc0f81be3ea7dd9f0fc3f5c728d49e965
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295891"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="be0ce-103">Implementar la herramienta SEFAUtil en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="be0ce-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="be0ce-104">Implementación de la herramienta de SEFAUtil de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="be0ce-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="be0ce-105">Para implementar y administrar recogida de llamadas de grupo, debe usar el Skype para la versión de la herramienta SEFAUtil Business Server.</span><span class="sxs-lookup"><span data-stu-id="be0ce-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="be0ce-106">Tiempo de ejecución de Microsoft Unified Communications Managed API (UCMA) 5 debe estar instalado en cualquier equipo donde va a ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="be0ce-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="be0ce-107">Descargarlo aquí: [Unified Communications Managed API 5.0 en tiempo de ejecución](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="be0ce-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="be0ce-108">También puede descargar el SDK de 5 de UCMA, que incluye el tiempo de ejecución, aquí: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="be0ce-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="be0ce-109">Puede ejecutar la herramienta de SEFAUtil de cualquier grupo de servidores Front-End en su implementación.</span><span class="sxs-lookup"><span data-stu-id="be0ce-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="be0ce-110">Para ejecutar la herramienta SEFAUtil debe ejecutar los pasos 1, 2 y 3 de la Skype para el Asistente para la implementación empresarial en el equipo de aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="be0ce-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="be0ce-111">SEFAUtil requiere estar presente en el almacén de configuración local, así como un certificado.</span><span class="sxs-lookup"><span data-stu-id="be0ce-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be0ce-112">Para obtener más información acerca de cómo ejecutar SEFAUtil, vea el artículo del blog, "[cómo obtener SEFAutil ejecutando?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="be0ce-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="be0ce-113">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="be0ce-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="be0ce-114">Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.</span><span class="sxs-lookup"><span data-stu-id="be0ce-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="be0ce-115">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="be0ce-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="be0ce-116">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="be0ce-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="be0ce-117">Si es necesario, definir un grupo de servidores de aplicaciones de confianza para el grupo de servidores Front-End donde va a ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="be0ce-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="be0ce-118">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="be0ce-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="be0ce-p104">Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="be0ce-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="be0ce-121">Si es preciso, puede usar otro puerto.</span><span class="sxs-lookup"><span data-stu-id="be0ce-121">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="be0ce-p105">Habilite la topología con los cambios. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="be0ce-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="be0ce-124">Si no lo ha hecho ya, descargue el Skype para la versión de la herramienta SEFAUtil Business Server desde [esta ubicación](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale en el grupo de aplicaciones de confianza que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="be0ce-124">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="be0ce-125">Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:</span><span class="sxs-lookup"><span data-stu-id="be0ce-125">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="be0ce-126">a.</span><span class="sxs-lookup"><span data-stu-id="be0ce-126">a.</span></span> <span data-ttu-id="be0ce-127">Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="be0ce-127">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="be0ce-128">b.</span><span class="sxs-lookup"><span data-stu-id="be0ce-128">b.</span></span> <span data-ttu-id="be0ce-129">Muestre la configuración de reenvío de llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="be0ce-129">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="be0ce-130">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="be0ce-130">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="be0ce-131">Aparecerá la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="be0ce-131">The call forwarding settings for the user will be displayed.</span></span>
    

