---
title: Configurar el almacén de contactos personales en equipos cliente para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal utilizado por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a><span data-ttu-id="4a8a8-103">Configurar el almacén de contactos personales en equipos cliente para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4a8a8-103">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4a8a8-104">**Resumen:** Configurar el almacén de contactos personal utilizado por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4a8a8-105">Si está integrando Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, debe configurar el almacén de contactos personal en los equipos cliente ejecutan Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-105">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="4a8a8-106">En concreto, debe configurar Skype para negocio utiliza Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="4a8a8-107">Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="4a8a8-108">Tenga en cuenta que esto no es necesario en equipos con Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="4a8a8-109">Para configurar este valor en un solo equipo, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="4a8a8-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="4a8a8-110">En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="4a8a8-111">En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="4a8a8-112">En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="4a8a8-113">Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="4a8a8-114">Después de crea el nuevo valor, escriba PersonalContactStoreOverride y, a continuación, presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="4a8a8-115">Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="4a8a8-116">Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="4a8a8-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="4a8a8-117">Para obtener más información, consulte la documentación de directiva de grupo en [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="4a8a8-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

