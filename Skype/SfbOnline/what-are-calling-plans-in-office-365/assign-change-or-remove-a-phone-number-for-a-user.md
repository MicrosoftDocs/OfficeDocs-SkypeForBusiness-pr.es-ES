---
title: Asignar, cambiar o quitar un número de teléfono para un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Aprenda a asignar, cambiar o quitar un número de teléfono de trabajo para sus usuarios de Skype for Business, de forma que los clientes y las empresas externas puedan llamar.
ms.openlocfilehash: a522e4fd6cbd41c34b2547ab6be0f7590de0a8b3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860595"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="91272-103">Asignar, cambiar o quitar un número de teléfono para un usuario</span><span class="sxs-lookup"><span data-stu-id="91272-103">Assign, change or remove a phone number for a user</span></span>

<span data-ttu-id="91272-104">Al configurar planes de llamada en Office 365, asigna números de teléfono a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="91272-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="91272-105">En el cliente de Microsoft Teams, se mostrará el número de teléfono que se asigna al hacer clic en **Llamadas**.</span><span class="sxs-lookup"><span data-stu-id="91272-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Número de teléfono del usuario que se muestra en Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="91272-107">En el cliente de Skype for Business, el número de teléfono que asigna aparecerá en el cuadro de **Teléfono de trabajo** y el usuario no lo puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="91272-107">The phone number you assign will be listed in the **This Work Phone** box in their Skype for Business client and can't be changed by a user.</span></span>
  
![El número de teléfono de trabajo aparece atenuado.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="91272-109">Si quiere [Cambiar su número de teléfono para Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) y el número de teléfono en la aplicación Skype for Business no se puede cambiar o está atenuado, esto significa que ha sido configurado por un administrador y que no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="91272-109">If they want to [Change my phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) \*\* and the phone number in the Skype for Business app can't be changed or is grayed out\*\*, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="91272-110">Al configurar usuarios para que puedan realizar y recibir llamadas de teléfono, primero tiene que usar el Centro de administración de Skype for Business y asignar un número de teléfono, pero puede cambiar o quitar el número de teléfono si es necesario.</span><span class="sxs-lookup"><span data-stu-id="91272-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="91272-111">Para obtener información sobre cómo obtener planes de llamada en Office 365 y su coste, vea [Licencias complementarias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="91272-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="91272-112">Para ver si un usuario tiene una licencia asignada, vaya al **Centro de administración de Skype for Business** > **Voz** > **Usuarios de voz** y seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="91272-112">One way to see if a user has a license assigned is in the **Skype for Business admin center** > **Voice** > **Voice users** and select the user.</span></span> <span data-ttu-id="91272-113">Si hay una licencia asignada, esta se mostrará en **Licencia asignada**.</span><span class="sxs-lookup"><span data-stu-id="91272-113">If a license is assigned, it will be listed under the **Assigned license**.</span></span> <span data-ttu-id="91272-114">Debe utilizar el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="91272-114">You can use the Office 365 admin center though too.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="91272-115">Asignar un número de teléfono a un usuario</span><span class="sxs-lookup"><span data-stu-id="91272-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="91272-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Uso del centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="91272-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="91272-117">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="91272-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="91272-118">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="91272-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="91272-119">En el panel de navegación izquierdo, haga clic en **Voz** > **Usuarios de voz**.</span><span class="sxs-lookup"><span data-stu-id="91272-119">In the left navigation, **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="91272-120">Para poder ver la opción **Voz** en el panel de navegación izquierdo del Centro de administración de Skype for Business, primero tiene que adquirir como mínimo una **licencia de Enterprise E5**, una licencia complementaria de **Sistema telefónico** o una licencia complementaria de **Audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="91272-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="91272-121">En la página **Usuarios de voz**, busque y seleccione el usuario o los usuarios a los que desea asignar un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="91272-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="91272-122">En el panel Acción, haga clic en **Asignar número**.</span><span class="sxs-lookup"><span data-stu-id="91272-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="91272-123">En la página **Asignar número**, en la lista **Seleccione el número que desea asignar**, seleccione el número de teléfono para el usuario.</span><span class="sxs-lookup"><span data-stu-id="91272-123">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="91272-124">Si no ve los números de teléfono enumerados, en primer lugar debe [obtener los números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="91272-124">If you don't see any phone numbers listed, you need to go Getting Skype for Business phone numbers for your users first or If you use the Skype for Business admin center  Voice  Phone numbers page > click Add then New user numbers.</span></span> <span data-ttu-id="91272-125">O bien, si usa el **Centro de administración de Skype for Business** > **Voz** > página de**Números de teléfono**, haga clic en **Agregar**y, a continuación, haga clic en **Nuevo número de usuario**.</span><span class="sxs-lookup"><span data-stu-id="91272-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="91272-126">Para asignar o cambiar la dirección de emergencia asociada, en **Seleccionar una ubicación de emergencia validada**, seleccione la ubicación en la lista o, si tiene varias ubicaciones definidas, escriba el nombre de la ciudad en el cuadro de búsqueda y haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="91272-126">To assign or change the associated emergency address under Select validated emergency location, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
8. <span data-ttu-id="91272-127">Después de asignar el número de teléfono y la ubicación de emergencia, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="91272-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91272-128">Debido a la latencia entre Office 365 y Skype for Business Online, es posible que el proceso para habilitar a los usuarios tarde hasta 24 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="91272-128">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled for PSTN Calling after you assign them licenses.</span></span> <span data-ttu-id="91272-129">Si después de 24 horas el número de teléfono no está asignado correctamente, [contacte al soporte técnico para productos de empresa: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="91272-129">If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="91272-130">Estamos aquí para ayudarle.</span><span class="sxs-lookup"><span data-stu-id="91272-130">We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="91272-131">Cambiar un número de teléfono de un usuario</span><span class="sxs-lookup"><span data-stu-id="91272-131">To change a phone number for a user</span></span>
 
<span data-ttu-id="91272-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Uso del centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="91272-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="91272-133">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="91272-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="91272-134">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="91272-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="91272-135">En el panel de navegación izquierdo, haga clic en **Voz** > **Usuarios de voz**.</span><span class="sxs-lookup"><span data-stu-id="91272-135">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="91272-136">En la página **Usuarios de voz**, busque y seleccione el usuario o los usuarios cuyos números de teléfono desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="91272-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="91272-137">En el panel Acción, en **Número asignado**, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="91272-137">In the Action pane, under **Assigned number** click **Change number**.</span></span> 
    
6. <span data-ttu-id="91272-138">En la página **Asignar número**, haga clic en **Cambiar número**.</span><span class="sxs-lookup"><span data-stu-id="91272-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="91272-139">En la página **Asignar número**, en **Seleccione el número que desea asignar**, use la lista para seleccionar el nuevo número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="91272-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="91272-140">Para cambiar la dirección de emergencia asociada, haga clic en **Cambiar ubicación** y en **Cambiar la dirección de emergencia a**, seleccione la ubicación en la lista, o si tiene varias ubicaciones definidas, escriba el nombre de la ciudad en el cuadro de búsqueda y haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="91272-140">To change the associated emergency address click Change location and under Change emergency address to, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
9. <span data-ttu-id="91272-141">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="91272-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="91272-142">Quitar un número de teléfono de un usuario</span><span class="sxs-lookup"><span data-stu-id="91272-142">To remove a phone number from a user</span></span>
 
<span data-ttu-id="91272-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Uso del centro de administración de Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="91272-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="91272-144">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="91272-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="91272-145">Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="91272-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="91272-146">En el panel de navegación izquierdo, haga clic en **Voz** > **Usuarios de voz**.</span><span class="sxs-lookup"><span data-stu-id="91272-146">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="91272-147">En la página **Usuarios de voz**, busque y seleccione el usuario o los usuarios cuyos números de teléfono desea quitar.</span><span class="sxs-lookup"><span data-stu-id="91272-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="91272-148">En el panel Acción, en **Número asignado**, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="91272-148">In the Action pane, under **Assigned number** click **Remove**.</span></span> 
    
6. <span data-ttu-id="91272-149">En la página **¿Quiere quitar el número asignado seleccionado?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="91272-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="91272-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="91272-150">Related topics</span></span>
[<span data-ttu-id="91272-151">¿Qué es la validación de direcciones?</span><span class="sxs-lookup"><span data-stu-id="91272-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="91272-152">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="91272-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="91272-153">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="91272-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="91272-154">[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="91272-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 