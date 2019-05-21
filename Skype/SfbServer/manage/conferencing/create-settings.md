---
title: Crear una configuración de reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumen: Aprenda a crear valores de configuración de reuniones en Skype empresarial Server.'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293847"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f3d81-103">Crear una configuración de reunión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3d81-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f3d81-104">**Resumen:** Aprenda a crear parámetros de configuración de reuniones en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f3d81-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="f3d81-105">Puede crear valores de configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f3d81-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f3d81-106">Crear parámetros de configuración de reunión con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3d81-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f3d81-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f3d81-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f3d81-108">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f3d81-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f3d81-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="f3d81-110">En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f3d81-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="f3d81-p101">Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="f3d81-p102">Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="f3d81-p103">Para redirigir a los participantes que realizaron la llamada desde una red telefónica conmutada (RTC) a través de la sala de espera, desactive la casilla **Los autores de llamadas RTC no pasan por la sala de espera**. Normalmente, los participantes que efectúen la llamada desde la RTC obtendrán acceso directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="f3d81-119">Para configurar quién puede ser moderador en una reunión, en **Designar como moderador**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3d81-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="f3d81-120">Para que solo sea moderador el organizador, haga clic en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="f3d81-p104">Para que solo sean moderadores los participantes que pertenezcan a la organización, haga clic en **Compañía**. Esta es la configuración que se aplica normalmente.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="f3d81-123">Para que cualquier participante sea moderador, haga clic en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="f3d81-p105">Para que el moderador pueda seleccionar un tipo de conferencia cuando se programe una reunión, desactive la casilla **Tipo de conferencia asignada de forma predeterminada**. Normalmente, el tipo de conferencia se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="f3d81-p106">Para evitar que se admitan automáticamente a usuarios anónimos (sin autenticar), desactive la casilla **Admitir usuarios anónimos de forma predeterminada**. Normalmente, los usuarios anónimos se admiten automáticamente en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="f3d81-128">Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3d81-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="f3d81-129">Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB.</span><span class="sxs-lookup"><span data-stu-id="f3d81-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="f3d81-130">Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión.</span><span class="sxs-lookup"><span data-stu-id="f3d81-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="f3d81-131">Si no incluye una dirección URL de ayuda personalizada, la dirección URL de la ayuda predeterminada para Skype empresarial se mostrará en la invitación.</span><span class="sxs-lookup"><span data-stu-id="f3d81-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="f3d81-p108">Para personalizar el logotipo que aparece en la invitación a la reunión, en **dirección URL del logotipo** introduzca la ubicación del logotipo. El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles.</span><span class="sxs-lookup"><span data-stu-id="f3d81-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="f3d81-134">Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, introduzca la ubicación del texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="f3d81-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="f3d81-135">Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, introduzca la ubicación del texto legal.</span><span class="sxs-lookup"><span data-stu-id="f3d81-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="f3d81-136">Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="f3d81-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="f3d81-137">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f3d81-138">Crear parámetros de configuración de reunión con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3d81-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f3d81-139">Para crear opciones de configuración de reunión, use el cmdlet **New-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f3d81-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="f3d81-140">El siguiente comando crea un conjunto de opciones de configuración de reunión para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="f3d81-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="f3d81-141">Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="f3d81-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="f3d81-p109">Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="f3d81-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="f3d81-p110">Puede establecer varios valores de propiedad incluyendo varios parámetros. Por ejemplo, el siguiente comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:</span><span class="sxs-lookup"><span data-stu-id="f3d81-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="f3d81-146">Para obtener más información, incluida una lista completa de parámetros, consulte [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f3d81-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

