---
title: Configurar el almacén de contactos personales en los equipos cliente de Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal utilizado por los clientes heredados.'
ms.openlocfilehash: 5545f3c0f993b1974f59e90c0b6672f3ebd246e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894263"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="bf30e-103">Configurar el almacén de contactos personales en los equipos cliente de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bf30e-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="bf30e-104">Si va a integrar Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, a continuación, debe configurar el almacén de contactos personal utilizado por los clientes.</span><span class="sxs-lookup"><span data-stu-id="bf30e-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="bf30e-105">En concreto, debe configurar Skype para la empresa utilizar Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión.</span><span class="sxs-lookup"><span data-stu-id="bf30e-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="bf30e-106">Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="bf30e-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf30e-107">El siguiente procedimiento sólo es necesario para los clientes mediante el cliente de Lync 2010 o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="bf30e-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="bf30e-108">El cliente de Lync 2013 y todos los Skype para clientes empresariales no tendrán la opción de omitir la configuración de almacén de contactos.</span><span class="sxs-lookup"><span data-stu-id="bf30e-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="bf30e-109">Para configurar este valor en un solo equipo, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="bf30e-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="bf30e-110">En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bf30e-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="bf30e-111">En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="bf30e-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="bf30e-112">En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="bf30e-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="bf30e-113">Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="bf30e-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="bf30e-114">Tras crear el nuevo valor, escriba PersonalContactStoreOverride y presione ENTRAR para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="bf30e-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="bf30e-115">Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.</span><span class="sxs-lookup"><span data-stu-id="bf30e-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="bf30e-116">Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf30e-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="bf30e-117">Para obtener información detallada sobre cómo hacer esto en 10 de Windows, vea el artículo [crear un objeto de directiva de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="bf30e-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
