---
title: Implementar la herramienta SEFAUtil en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implementar la herramienta SEFAUtil en Skype Empresarial Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812390"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="50246-103">Implementar la herramienta SEFAUtil en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="50246-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="50246-104">Implementar la herramienta SEFAUtil en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="50246-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="50246-105">Para implementar y administrar la atención de llamadas grupales, debe usar la versión de Skype Empresarial Server de la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="50246-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="50246-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime debe estar instalado en cualquier equipo en el que planee ejecutar la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="50246-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="50246-107">Descárbalo aquí: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="50246-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="50246-108">También puede descargar el SDK de UCMA 5, que incluye el tiempo de ejecución, aquí: [SDK de UCMA 5.0.](https://www.microsoft.com/download/details.aspx?id=47345)</span><span class="sxs-lookup"><span data-stu-id="50246-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="50246-109">Puede ejecutar la herramienta SEFAUtil en cualquier grupo de servidores front-end de la implementación.</span><span class="sxs-lookup"><span data-stu-id="50246-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="50246-110">Para ejecutar la herramienta SEFAUtil, debe ejecutar los pasos 1, 2 y 3 desde el Asistente para la implementación de Skype Empresarial en el equipo de la aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="50246-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="50246-111">SEFAUtil requiere que el almacén de configuración local esté presente, así como un certificado.</span><span class="sxs-lookup"><span data-stu-id="50246-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50246-112">Para obtener más información sobre cómo ejecutar SEFAUtil, consulte el artículo del blog " ¿Cómo hacer[que SEFAutil se ejecute?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="50246-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="50246-113">Para implementar SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="50246-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="50246-114">Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados.**</span><span class="sxs-lookup"><span data-stu-id="50246-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="50246-115">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="50246-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="50246-116">La herramienta SEFAUtil solo se puede ejecutar en un equipo que forma parte de un grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="50246-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="50246-117">Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end donde planee ejecutar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="50246-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="50246-118">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="50246-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="50246-119">FQDN del grupo de servidores: el FQDN del servidor o grupo de servidores que hospedará la aplicación SEFAUtil (normalmente un servidor front-end o grupo de servidores de Skype Empresarial).</span><span class="sxs-lookup"><span data-stu-id="50246-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="50246-120">FQDN del registrador de grupo: el FQDN del servidor front-end de Skype Empresarial o del grupo asociado a este grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="50246-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="50246-121">Sitio del grupo de servidores: el identificador de sitio del sitio en el que se encuentra este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="50246-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="50246-122">Defina la herramienta SEFAUtil como una aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="50246-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="50246-123">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="50246-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="50246-124">Puede usar un puerto diferente si es necesario.</span><span class="sxs-lookup"><span data-stu-id="50246-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="50246-125">Habilite la topología con los cambios.</span><span class="sxs-lookup"><span data-stu-id="50246-125">Enable the topology with your changes.</span></span> <span data-ttu-id="50246-126">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="50246-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="50246-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span><span class="sxs-lookup"><span data-stu-id="50246-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="50246-128">Compruebe que la herramienta SEFAUtil se está ejecutando correctamente, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="50246-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="50246-129">a.</span><span class="sxs-lookup"><span data-stu-id="50246-129">a.</span></span> <span data-ttu-id="50246-130">Ejecuta la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de reenvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="50246-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="50246-131">b.</span><span class="sxs-lookup"><span data-stu-id="50246-131">b.</span></span> <span data-ttu-id="50246-132">Muestra la configuración de reenvío de llamadas de un usuario.</span><span class="sxs-lookup"><span data-stu-id="50246-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="50246-133">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="50246-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="50246-134">Se mostrará la configuración de reenvío de llamadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="50246-134">The call forwarding settings for the user will be displayed.</span></span>
    

