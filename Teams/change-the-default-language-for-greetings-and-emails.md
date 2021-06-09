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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Obtenga información sobre cómo configurar Microsoft Teams y Skype Empresarial usar otro idioma para el saludo predeterminado del correo de voz de su organización.
ms.openlocfilehash: f211a5e160ce05707a454e5100409840e4c781ac
ms.sourcegitcommit: eca3f5e83e4a07be197936db19f539cbfa2c2bd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52804527"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="5bdb9-103">Cambiar el idioma predeterminado en los saludos y los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="5bdb9-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="5bdb9-104">Si es un administrador [global,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)puede configurar Skype Empresarial para reproducir el saludo predeterminado del correo de voz en otro idioma.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="5bdb9-105">El saludo predeterminado del sistema es similar a: "Deje un mensaje para John Smith.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="5bdb9-106">Grabe su mensaje después del tono.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-106">After the tone, please record your message.</span></span> <span data-ttu-id="5bdb9-107">Cuando termine la grabación, cuelgue o presione la tecla almohadilla para tener acceso a otras opciones".</span><span class="sxs-lookup"><span data-stu-id="5bdb9-107">When you finish recording, hang up, or press the pound key for more options."</span></span>
  
 <span data-ttu-id="5bdb9-108">**Primero, lea esta información importante:**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="5bdb9-109">**Los idiomas disponibles dependen de la ubicación de su organización**.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="5bdb9-110">Por ejemplo, si su organización está en Estados Unidos, puede definir su idioma predeterminado como inglés o español.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="5bdb9-111">Si su organización está ubicada en Canadá, puede elegir entre inglés y francés.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="5bdb9-112">Para obtener una lista de los idiomas admitidos en Teams y Skype Empresarial, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-112">For a list of supported languages in Teams and Skype for Business, see the following:</span></span>
  - [<span data-ttu-id="5bdb9-113">Microsoft Teams idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="5bdb9-113">Microsoft Teams supported languages</span></span>](languages-for-voicemail-greetings-and-messages.md)
  - [<span data-ttu-id="5bdb9-114">Skype Empresarial idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="5bdb9-114">Skype for Business supported languages</span></span>](/skypeforbusiness/what-is-phone-system-in-office-365/phone-system-voicemail/languages-for-voicemail-greetings-and-messages)

- <span data-ttu-id="5bdb9-115">**Cambiar los idiomas de los mensajes de correo de voz y de correo de voz de cada usuario.**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-115">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="5bdb9-116">Puede cambiar el idioma preferido para los usuarios, lo que cambiará el idioma de sus mensajes de correo de voz y saludo de correo de voz enviados a su buzón Outlook correo de voz.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-116">You can change the preferred language for users, which will change the language of their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="5bdb9-117">Para obtener más información, vea [Cómo establecer la](/office365/troubleshoot/access-management/set-language-and-region)configuración de idioma y región para Microsoft 365 o Office 365 .</span><span class="sxs-lookup"><span data-stu-id="5bdb9-117">For more information, see [How to set language and region settings for Microsoft 365 or Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

  > [!NOTE]
  > <span data-ttu-id="5bdb9-118">Los usuarios pueden cambiar el idioma del saludo mediante su configuración después de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-118">Users can change their own greeting language through their settings after they sign in.</span></span> <span data-ttu-id="5bdb9-119">Para obtener más información, vea Cambiar el idioma de visualización y la zona [horaria en Microsoft 365 para empresas](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="5bdb9-119">For more information, see [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="5bdb9-120">**¿Desea grabar el mensaje del correo de voz saliente?**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-120">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="5bdb9-121">Consulte [Comprobar el correo de voz y las opciones de Skype Empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="5bdb9-121">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="5bdb9-122">Por Microsoft Teams: los usuarios pueden cambiar la configuración del correo de voz desde la [Teams del cliente de escritorio](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="5bdb9-122">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="5bdb9-123">**¿Desea cambiar el idioma del mensaje de voz?**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-123">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="5bdb9-124">Para Skype Empresarial - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) y elija un nuevo idioma en Idioma **rápido.**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-124">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="5bdb9-125">Por Microsoft Teams: los usuarios pueden cambiar el saludo del correo de voz desde la [Teams de cliente de escritorio](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="5bdb9-125">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="5bdb9-126">Cambiar el idioma del sistema para todos los usuarios de la organización</span><span class="sxs-lookup"><span data-stu-id="5bdb9-126">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="5bdb9-127">Inicie sesión con su cuenta [de administrador global](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="5bdb9-127">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="5bdb9-128">En el Microsoft 365 de administración, **elija Configuración**  >  **Configuración** de la  >  **organización.**</span><span class="sxs-lookup"><span data-stu-id="5bdb9-128">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span>

     ![Captura de pantalla que muestra Configuración y, a continuación, perfil de organización.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="5bdb9-130">Elija **Edit**.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-130">Choose **Edit**.</span></span>

    ![Captura de pantalla que muestra la opción Editar.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="5bdb9-132">Seleccione un idioma en la lista **Idioma preferido** para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-132">Select a language from the **Preferred language** list for everyone in your organization.</span></span>

5. <span data-ttu-id="5bdb9-133">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-133">Choose **Save**.</span></span>

## <a name="related-articles-for-the-admin"></a><span data-ttu-id="5bdb9-134">Artículos relacionados para el administrador</span><span class="sxs-lookup"><span data-stu-id="5bdb9-134">Related articles for the admin</span></span>

- [<span data-ttu-id="5bdb9-135">Sistema telefónico y Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="5bdb9-135">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="5bdb9-136">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="5bdb9-136">Set up Calling Plans</span></span>](set-up-calling-plans.md)

- [<span data-ttu-id="5bdb9-137">Planear Sistema telefónico en Microsoft 365 o Office 365 con conectividad RTC local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5bdb9-137">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

## <a name="related-topics"></a><span data-ttu-id="5bdb9-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5bdb9-138">Related topics</span></span>

- [<span data-ttu-id="5bdb9-139">Cambiar el idioma de visualización y la zona horaria en Microsoft 365 o Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5bdb9-139">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)

- <span data-ttu-id="5bdb9-140">[Agregar un idioma o establecer preferencias de idioma en Office 2010 y versiones posteriores](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="5bdb9-140">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>

- [<span data-ttu-id="5bdb9-141">Habilitar o cambiar el idioma de distribución del teclado</span><span class="sxs-lookup"><span data-stu-id="5bdb9-141">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
