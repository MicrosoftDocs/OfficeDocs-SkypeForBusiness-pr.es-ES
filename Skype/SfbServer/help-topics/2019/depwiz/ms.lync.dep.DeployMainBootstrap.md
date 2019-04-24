---
title: Instalar o quitar componentes de Skype Empresarial Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para instalar y activar, desactivar o desinstalar Skype para componentes de servidor empresarial, utiliza el paso 2: instalar o desinstalar componentes de servidor de Skype. Debe iniciar sesión en como administrador local en el equipo que está instalando o modificar y deben poder leer los usuarios de los servicios de dominio de Active Directory y grupos en el dominio actual. Para empezar, haga clic en Ejecutar. Una vez hecho esto, se leerá la definición de topología basada en almacenes de administración central. Se instalarán los componentes de software necesarios y se configurarán de acuerdo con el rol definido en el almacén de administración central. Una vez finalizada la instalación, revise el resumen y haga clic en Finalizar.'
ms.openlocfilehash: cc16e843159cf0d06614f2ba3a095112664fe2fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216203"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="92d61-108">Instalar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="92d61-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="92d61-109">Para instalar y activar, desactivar o desinstalar Skype para los componentes de Business Server, se utiliza **paso 2: instalar o desinstalar componentes de servidor de Skype**.</span><span class="sxs-lookup"><span data-stu-id="92d61-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="92d61-110">Debe iniciar sesión en como administrador local en el equipo que está instalando o modificar y deben poder leer los usuarios de los servicios de dominio de Active Directory y grupos en el dominio actual.</span><span class="sxs-lookup"><span data-stu-id="92d61-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="92d61-111">Para empezar, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92d61-111">To begin, click **Run**.</span></span> <span data-ttu-id="92d61-112">Una vez hecho esto, se leerá la definición de topología basada en almacenes de administración central.</span><span class="sxs-lookup"><span data-stu-id="92d61-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="92d61-113">Se instalarán los componentes de software necesarios y se configurarán de acuerdo con el rol definido en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="92d61-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="92d61-114">Una vez finalizada la instalación, revise el resumen y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="92d61-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="92d61-115">Si necesita revisar los archivos de registro que se crean mediante el Asistente para la implementación, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Active Directory que se ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="92d61-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="92d61-116">Por ejemplo, si el usuario iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="92d61-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="92d61-117">Si previamente instaló Skype para los componentes de Business Server en este equipo, el Asistente para la implementación reconocerá esto y el botón en el paso 2 se mostrará como **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="92d61-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="92d61-118">De este modo, puede realizar el paso tantas veces como desee para configurar el servidor correctamente o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="92d61-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

