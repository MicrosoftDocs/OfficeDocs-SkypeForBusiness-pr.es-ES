---
title: Habilitar los dispositivos de salas de equipos para unirse a reuniones de terceros
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar la organización y los dispositivos de salas de equipos para admitir la Unión de reuniones de terceros con Cisco WebEx y el zoom.
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682389"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="8822a-103">Habilitar los dispositivos de la sala de equipos para unirse a reuniones de terceros</span><span class="sxs-lookup"><span data-stu-id="8822a-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="8822a-104">Los dispositivos de salas de Microsoft Teams admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, también conocidas como Unión directa de invitados.</span><span class="sxs-lookup"><span data-stu-id="8822a-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="8822a-105">Cuando está habilitado, puede usar un dispositivo de salas de equipos para unirse a reuniones hospedadas en Cisco WebEx y acercar la forma tan sencilla como puede unirse a reuniones hospedadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8822a-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="8822a-106">Para poder unirse a reuniones de terceros desde un dispositivo de salas de equipos, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8822a-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="8822a-107">Configure el buzón de correo del dispositivo salas de Exchange Online para que procese invitaciones para reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="8822a-108">Asegúrese de que su organización no tiene ninguna directiva que le impida conectarse a servicios de reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="8822a-109">Configure los dispositivos de las salas de equipos para permitir reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="8822a-110">En las secciones siguientes se muestra cómo realizar cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8822a-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="8822a-111">Paso 1: permitir el procesamiento de invitaciones al calendario para reuniones de terceros</span><span class="sxs-lookup"><span data-stu-id="8822a-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="8822a-112">Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde un dispositivo de salas de equipo es establecer las reglas de procesamiento del calendario para el buzón de correo de la sala de Exchange online del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8822a-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="8822a-113">El buzón de sala debe permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="8822a-114">Para configurar estas opciones de buzón de sala con el cmdlet [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8822a-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="8822a-115">Conéctese a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8822a-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="8822a-116">Para obtener más información, vea [conectarse a Exchange Online PowerShell con autenticación básica](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [conectarse a Exchange Online PowerShell con la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), según el método de autenticación.</span><span class="sxs-lookup"><span data-stu-id="8822a-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="8822a-117">Obtenga el nombre principal de usuario (UPN) del buzón de sala si no lo conoce ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8822a-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="8822a-118">Busque el nombre del buzón de sala asociado a su dispositivo de salas de equipos y tome nota de su UPN.</span><span class="sxs-lookup"><span data-stu-id="8822a-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="8822a-119">Después de encontrar el UPN del buzón de sala, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8822a-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="8822a-120">Reemplazar `<UserPrincipalName>` por el UPN del buzón de sala:</span><span class="sxs-lookup"><span data-stu-id="8822a-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="8822a-121">Obtenga más información sobre [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="8822a-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="8822a-122">Paso 2: configurar la protección contra amenazas de Office 365 y la reescritura de vínculos</span><span class="sxs-lookup"><span data-stu-id="8822a-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="8822a-123">Para habilitar la experiencia de combinación única, la información del vínculo para unirse a la reunión de la reunión de terceros debe estar presente y es legible en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="8822a-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="8822a-124">Si su organización usa la característica de [vínculos seguros de la protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) , o si usa una solución de terceros que analice todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de la combinación de reuniones para que el dispositivo de las salas de equipos no reconozca la reunión.</span><span class="sxs-lookup"><span data-stu-id="8822a-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="8822a-125">Para asegurarse de que esto no suceda, debe agregar las direcciones URL del servicio de reunión de terceros a la lista de vínculos seguros de ATP "no rescribir" o a la lista de excepciones de reescritura de direcciones URL de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="8822a-126">Para agregar direcciones URL de los servicios de reuniones de terceros a la lista de vínculos seguros de ATP "do not Write", siga los pasos que se indican en [configurar una lista de direcciones URL de hacer y desescritura personalizada con vínculos seguros de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8822a-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="8822a-127">Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a la lista de excepciones de reescritura de URL.</span><span class="sxs-lookup"><span data-stu-id="8822a-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="8822a-128">Estas son algunas entradas de ejemplo que es posible que tenga que agregar a la lista de vínculos seguros de ATP "do not Write" o a la lista de excepciones de reescritura de direcciones URL de terceros:</span><span class="sxs-lookup"><span data-stu-id="8822a-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="8822a-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="8822a-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="8822a-130">**Zoom** `*.zoom.us*` , `*.zoom.com*``*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="8822a-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="8822a-131">Para obtener una lista completa de las direcciones URL que se agregarán a la lista de vínculos seguros de ATP "do not Write" o a la lista de excepciones de reescritura de direcciones URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros en el que desea aceptar las invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="8822a-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="8822a-132">Agregue solo direcciones URL en las que confía a la lista de vínculos seguros de ATP "no rescribir" o lista de excepciones de reescritura de direcciones URL de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="8822a-133">Paso 3: habilitar las reuniones de terceros en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="8822a-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="8822a-134">El último paso que debe realizar es permitir que cada dispositivo de salas de equipos se una a reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="8822a-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="8822a-135">Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas.</span><span class="sxs-lookup"><span data-stu-id="8822a-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="8822a-136">Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes a los del buzón de sala del dispositivo, tendrá que agregarlos al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8822a-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="8822a-137">Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="8822a-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="8822a-138">Usar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8822a-138">Use device settings</span></span>

<span data-ttu-id="8822a-139">Para configurar el dispositivo de salas de equipos con su pantalla táctil, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8822a-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="8822a-140">En el dispositivo de salas de Microsoft Teams, seleccione **más...**</span><span class="sxs-lookup"><span data-stu-id="8822a-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="8822a-141">Seleccione **configuración** y, a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8822a-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="8822a-142">Vaya a la ficha **reuniones** y seleccione **Cisco WebEx**, **zoom** o ambos.</span><span class="sxs-lookup"><span data-stu-id="8822a-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="8822a-143">Si desea unirse a las reuniones con el nombre de usuario y la dirección de correo electrónico asociados con el buzón de sala, seleccione **unirse con la información de la sala**.</span><span class="sxs-lookup"><span data-stu-id="8822a-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="8822a-144">Si desea unirse a las reuniones con un nombre de usuario y una dirección de correo electrónico alternativos, seleccione **unirse con la información personalizada** y escriba el nombre de usuario y la dirección de correo electrónico que desea usar.</span><span class="sxs-lookup"><span data-stu-id="8822a-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="8822a-145">Seleccione **Guardar y salir**.</span><span class="sxs-lookup"><span data-stu-id="8822a-145">Select **Save and exit**.</span></span> <span data-ttu-id="8822a-146">El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="8822a-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="8822a-147">Usar el archivo de configuración SkypeSettings.xml</span><span class="sxs-lookup"><span data-stu-id="8822a-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="8822a-148">La siguiente configuración se puede Agregar al archivo que se `SkypeSettings.xml` encuentra en `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="8822a-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="8822a-149">Para obtener más información sobre el `SkypeSettings.xml` archivo, consulte [administrar de forma remota la configuración de una consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="8822a-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="8822a-150">Para habilitar las reuniones de Cisco WebEx, establezca el `WebExMeetingsEnabled` elemento XML en **true**, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8822a-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="8822a-151">Para habilitar las reuniones de zoom, establezca el `ZoomMeetingsEnabled` elemento XML en **true**, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8822a-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="8822a-152">De manera opcional, puede especificar un nombre de usuario y una dirección de correo electrónico personalizados para unirse a reuniones de terceros con los siguientes elementos XML.</span><span class="sxs-lookup"><span data-stu-id="8822a-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="8822a-153">Si los valores que proporciona no son válidos, el dispositivo salas de equipos predeterminado usará el nombre de usuario y la dirección de correo electrónico del buzón de sala.</span><span class="sxs-lookup"><span data-stu-id="8822a-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="8822a-154">Para unirse a una reunión de Cisco WebEx desde un dispositivo de salas de equipos, la reunión de Cisco debe estar hospedada mediante la versión WBS 40,7 o posterior de la aplicación web Cisco WebEx.</span><span class="sxs-lookup"><span data-stu-id="8822a-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

