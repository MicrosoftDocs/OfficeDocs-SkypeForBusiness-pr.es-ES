---
title: Establecer el PIN para transferir números a un nuevo proveedor de servicios
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Para transferir o portar números de teléfono de Skype for Business Online a otro proveedor u operador de servicios telefónicos, debe establecer manualmente un PIN. Después de establecer el PIN, necesitará incluirlo en la solicitud para portar un número de teléfono.
ms.openlocfilehash: ef688c6aa7aabd1880513994236cb62353eab665
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890112"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="3e1ca-104">Establecer el PIN para transferir números a un nuevo proveedor de servicios</span><span class="sxs-lookup"><span data-stu-id="3e1ca-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="3e1ca-105">Para transferir o *portar*  números de teléfono de Skype for Business Online otro proveedor u operador de servicios telefónicos, deberá configurar manualmente un PIN.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="3e1ca-106">Después de establecer el PIN, necesitará incluirlo en la solicitud para portar un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3e1ca-107">Solo se utiliza un PIN de portabilidad en las organizaciones de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="3e1ca-108">Para obtener más información acerca de la transferencia y porte de números de teléfono, vea [Transferir números de teléfono para Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="3e1ca-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="3e1ca-109">Esta es la información específica acerca de este PIN que debe conocer:</span><span class="sxs-lookup"><span data-stu-id="3e1ca-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="3e1ca-110">Si no se ha configurado un PIN, no podrá transferir o portar números de teléfono de Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="3e1ca-111">El PIN puede contener de 6 a 10 dígitos (números).</span><span class="sxs-lookup"><span data-stu-id="3e1ca-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="3e1ca-112">No puede contener letras o caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="3e1ca-113">El valor predeterminado de PIN está en blanco, pero si se inserta uno, no se puede quitar o establecer de nuevo en blanco.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="3e1ca-114">Tras especificar un PIN, puede actualizarlo o cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="3e1ca-115">Configurar el PIN</span><span class="sxs-lookup"><span data-stu-id="3e1ca-115">Set up your PIN</span></span>

<span data-ttu-id="3e1ca-116">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="3e1ca-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="3e1ca-117">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3e1ca-118">Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para la empresa**.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3e1ca-119">En el panel de navegación izquierdo, elija **voz** > **pedidos de puerto**.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="3e1ca-120">Haga clic en **Configurar y administrar el PIN** que se usa para la transferencia o portabilidad de números a otro operador de servicios.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="3e1ca-121">En el panel **Establecer o cambiar el PIN de portabilidad**, escriba el PIN y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e1ca-122">Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="3e1ca-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3e1ca-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3e1ca-123">Related topics</span></span>
[<span data-ttu-id="3e1ca-124">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="3e1ca-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="3e1ca-125">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="3e1ca-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="3e1ca-126">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="3e1ca-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="3e1ca-127">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="3e1ca-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="3e1ca-128">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3e1ca-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

