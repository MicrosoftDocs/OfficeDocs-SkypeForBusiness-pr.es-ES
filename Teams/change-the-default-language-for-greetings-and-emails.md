---
title: Cambiar el idioma predeterminado en los saludos y los correos electrónicos
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Aprenda a configurar Skype Empresarial para usar otro idioma para el saludo del correo de voz predeterminado de su organización. '
ms.openlocfilehash: f36ab76f0a83fc71f9d7ca668020dcd30f4808d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283459"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="689db-103">Cambiar el idioma predeterminado en los saludos y los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="689db-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="689db-104">Si es [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), puede configurar Skype Empresarial para que reproduzca el saludo predeterminado del correo de voz en otro idioma.</span><span class="sxs-lookup"><span data-stu-id="689db-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="689db-105">El saludo predeterminado del sistema es similar a: "Deje un mensaje para John Smith.</span><span class="sxs-lookup"><span data-stu-id="689db-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="689db-106">Grabe su mensaje después del tono.</span><span class="sxs-lookup"><span data-stu-id="689db-106">After the tone, please record your message.</span></span> <span data-ttu-id="689db-107">Cuando termine la grabación, cuelgue o presione la tecla almohadilla para tener acceso a otras opciones".</span><span class="sxs-lookup"><span data-stu-id="689db-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="689db-108">**Primero, lea esta información importante:**</span><span class="sxs-lookup"><span data-stu-id="689db-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="689db-109">**Los idiomas disponibles dependen de la ubicación de su organización**.</span><span class="sxs-lookup"><span data-stu-id="689db-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="689db-110">Por ejemplo, si su organización está en Estados Unidos, puede definir su idioma predeterminado como inglés o español.</span><span class="sxs-lookup"><span data-stu-id="689db-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="689db-111">Si su organización está ubicada en Canadá, puede elegir entre inglés y francés.</span><span class="sxs-lookup"><span data-stu-id="689db-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="689db-112">Para obtener una lista de los idiomas admitidos, consulte [Idiomas de los saludos y mensajes del correo de voz de Skype Empresarial](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="689db-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="689db-p103">**No hay forma de cambiar el idioma del sistema para solo una persona de su organización.** Solo puede cambiar el idioma del saludo para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="689db-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="689db-115">Los usuarios pueden cambiar el idioma del saludo mediante su configuración después de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="689db-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="689db-116">**¿Desea grabar el mensaje del correo de voz saliente?**</span><span class="sxs-lookup"><span data-stu-id="689db-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="689db-117">Consulte [Comprobar el correo de voz y las opciones de Skype Empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="689db-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="689db-118">**¿Desea cambiar el idioma del mensaje del buzón de voz?**</span><span class="sxs-lookup"><span data-stu-id="689db-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="689db-119">Vaya a [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) y elija un nuevo idioma en el **idioma del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="689db-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="689db-120">Cambiar el idioma del sistema para todos los usuarios de la organización</span><span class="sxs-lookup"><span data-stu-id="689db-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="689db-121">Inicie sesión con su cuenta de [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="689db-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="689db-122">En el centro de administración de Microsoft 365, seleccione **configuración** > del perfil de la**organización**.</span><span class="sxs-lookup"><span data-stu-id="689db-122">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="689db-124">Elija **Edit**.</span><span class="sxs-lookup"><span data-stu-id="689db-124">Choose **Edit**.</span></span>
    
    ![Elija Editar.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="689db-126">Seleccione un idioma en la lista **Idioma preferido** para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="689db-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="689db-127">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="689db-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="689db-128">Artículos relacionados para el administrador</span><span class="sxs-lookup"><span data-stu-id="689db-128">Related articles for the admin</span></span>

- [<span data-ttu-id="689db-129">Sistema telefónico y Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="689db-129">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="689db-130">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="689db-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="689db-131">Planear un sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="689db-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="689db-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="689db-132">Related topics</span></span>

- [<span data-ttu-id="689db-133">Cambiar el idioma y la zona horaria de la interfaz de usuario en Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="689db-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="689db-134">[Agregar un idioma o establecer preferencias de idioma en Office 2010 y versiones posteriores](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="689db-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="689db-135">Habilitar o cambiar el idioma de distribución del teclado</span><span class="sxs-lookup"><span data-stu-id="689db-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
