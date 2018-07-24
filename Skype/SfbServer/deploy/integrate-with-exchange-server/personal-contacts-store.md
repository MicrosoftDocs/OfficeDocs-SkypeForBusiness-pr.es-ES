---
title: Configurar el almacén de contactos personales en los equipos cliente de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal usado 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server.'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012903"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a><span data-ttu-id="3470e-103">Configurar el almacén de contactos personales en los equipos cliente de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3470e-103">Configure the personal contacts store on client computers for Skype for Business Server</span></span>
 
<span data-ttu-id="3470e-104">**Resumen:** Configurar el almacén de contactos personal usado 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3470e-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="3470e-105">Si va a integrar Skype para Business Server y Exchange Server 2016 o Exchange Server 2013, debe configurar el almacén de contactos personal en los equipos de cliente que ejecutan Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="3470e-105">If you are integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="3470e-106">En concreto, debe configurar Skype para la empresa utilizar Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión.</span><span class="sxs-lookup"><span data-stu-id="3470e-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="3470e-107">Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="3470e-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="3470e-108">Tenga en cuenta que esto no es necesario en los equipos que ejecutan Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="3470e-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="3470e-109">Para configurar este valor en un solo equipo, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="3470e-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="3470e-110">En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3470e-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="3470e-111">En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3470e-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="3470e-112">En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="3470e-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="3470e-113">Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="3470e-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="3470e-114">Tras crear el nuevo valor, escriba PersonalContactStoreOverride y presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="3470e-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="3470e-115">Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.</span><span class="sxs-lookup"><span data-stu-id="3470e-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="3470e-116">Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3470e-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="3470e-117">Para obtener información detallada, vea la documentación de directiva de grupo en [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="3470e-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

