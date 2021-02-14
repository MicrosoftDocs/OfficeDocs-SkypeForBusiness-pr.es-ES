---
title: Habilitar dispositivos de salas de Teams para unirse a reuniones de terceros
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
description: En este artículo se describe cómo configurar su organización y los dispositivos de Salas de Teams para que admitan la unión a reuniones de terceros a Cisco WebEx y Zoom.
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682389"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="4e284-103">Habilitar dispositivos de salas de Teams para unirse a reuniones de terceros</span><span class="sxs-lookup"><span data-stu-id="4e284-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="4e284-104">Los dispositivos de salas de Microsoft Teams admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, lo que también se conoce como unión directa como invitado.</span><span class="sxs-lookup"><span data-stu-id="4e284-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="4e284-105">Cuando esté habilitado, puede usar un dispositivo de salas de Teams para unirse a reuniones hospedadas en Cisco WebEx y Zoom de la forma más sencilla posible para unirse a reuniones hospedadas en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4e284-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="4e284-106">Antes de unirse a reuniones de terceros desde un dispositivo de Salas de Teams, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e284-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="4e284-107">Configure el buzón de sala de Exchange Online del dispositivo salas de Teams para procesar invitaciones a reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="4e284-108">Asegúrese de que su organización no tenga directivas que le impidan conectarse a servicios de reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="4e284-109">Configure sus dispositivos de Salas de Teams para permitir reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="4e284-110">En las secciones siguientes se muestra cómo realizar cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4e284-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="4e284-111">Paso 1: Permitir el procesamiento de las invitaciones del calendario para las reuniones de terceros</span><span class="sxs-lookup"><span data-stu-id="4e284-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="4e284-112">Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde un dispositivo de salas de grupo es establecer las reglas de procesamiento del calendario del buzón de sala de Exchange Online del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e284-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="4e284-113">El buzón de sala necesita permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="4e284-114">Para establecer estas opciones de buzón de sala con el cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e284-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="4e284-115">Conéctese a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e284-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="4e284-116">Para obtener más información, vea Conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) con autenticación básica o Conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)usando multifactor de autenticación, dependiendo de su método de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4e284-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="4e284-117">Para obtener el nombre principal de usuario (UPN) del buzón de sala, ejecute el siguiente comando para obtener el nombre principal de usuario (UPN) del buzón de sala:</span><span class="sxs-lookup"><span data-stu-id="4e284-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="4e284-118">Busque el nombre del buzón de sala asociado a su dispositivo de salas de Teams y tome nota de su UPN.</span><span class="sxs-lookup"><span data-stu-id="4e284-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="4e284-119">Cuando encuentre el UPN del buzón de sala, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="4e284-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="4e284-120">Cambie `<UserPrincipalName>` por el UPN del buzón de sala:</span><span class="sxs-lookup"><span data-stu-id="4e284-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="4e284-121">Obtenga más información [sobre PowerShell de Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="4e284-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="4e284-122">Paso 2: Configurar la Protección contra amenazas de Office 365 y la reescritura de vínculos</span><span class="sxs-lookup"><span data-stu-id="4e284-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="4e284-123">Para habilitar la experiencia de unirse con un solo toque, la información del vínculo para unirse a la reunión de terceros debe estar presente y ser legible en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="4e284-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="4e284-124">Si su organización usa la característica vínculos seguros de protección contra amenazas avanzada de [Office 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o si usa una solución de terceros que analiza todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de unión a la reunión y hacer que la reunión no se pueda reconocer en el dispositivo de Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="4e284-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="4e284-125">Para asegurarse de que esto no ocurre, tiene que agregar las direcciones URL del servicio de reuniones de terceros a la lista de vínculos seguros de ATP "no se reescriba" ni a la lista de excepciones de reescritura de URL de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="4e284-126">Para agregar direcciones URL de servicio de reuniones de terceros a la lista de vínculos seguros de ATP "no reescribir", siga los pasos de Configurar una lista personalizada de url de no reescritura con vínculos seguros de [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="4e284-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="4e284-127">Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a su lista de excepciones de reescritura de URL.</span><span class="sxs-lookup"><span data-stu-id="4e284-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="4e284-128">Estas son algunas entradas de ejemplo que puede que necesite agregar a la lista de vínculos seguros de ATP "no reescribir" o a la lista de excepciones de reescritura de URL de terceros:</span><span class="sxs-lookup"><span data-stu-id="4e284-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="4e284-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="4e284-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="4e284-130">**Zoom,** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="4e284-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="4e284-131">Para obtener una lista completa de direcciones URL para agregar a la lista de vínculos seguros de ATP "no reescribir" o la lista de excepciones de reescritura de URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros del que desea aceptar invitaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="4e284-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="4e284-132">Agregue solo las direcciones URL en las que confía a la lista de vínculos seguros de ATP "no reescribir" ni a la lista de excepciones de reescritura de URL de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="4e284-133">Paso 3: Habilitar reuniones de terceros en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="4e284-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="4e284-134">El último paso que debe realizar es permitir que cada dispositivo de Salas de Teams se una a reuniones de terceros.</span><span class="sxs-lookup"><span data-stu-id="4e284-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="4e284-135">Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas.</span><span class="sxs-lookup"><span data-stu-id="4e284-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="4e284-136">Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes del buzón de sala del dispositivo, deberá agregarlos al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e284-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="4e284-137">Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="4e284-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="4e284-138">Usar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4e284-138">Use device settings</span></span>

<span data-ttu-id="4e284-139">Para configurar el dispositivo Salas de Teams con su pantalla táctil, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e284-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="4e284-140">En el dispositivo Salas de Microsoft Teams, seleccione **Más...**.</span><span class="sxs-lookup"><span data-stu-id="4e284-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="4e284-141">Seleccione **Configuración y,** a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e284-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="4e284-142">Vaya a la **pestaña Reuniones** y seleccione **Cisco WebEx,** **Zoom** o ambos.</span><span class="sxs-lookup"><span data-stu-id="4e284-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="4e284-143">Si quiere unirse a las reuniones con el nombre de usuario y la dirección de correo electrónico asociados al buzón de sala, seleccione **Unirse con la información de la sala.**</span><span class="sxs-lookup"><span data-stu-id="4e284-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="4e284-144">Si desea unirse a las reuniones con una  dirección de correo electrónico y un nombre de usuario alternativos, seleccione Unirse con información personalizada y escriba el nombre de usuario y la dirección de correo electrónico que le gustaría usar.</span><span class="sxs-lookup"><span data-stu-id="4e284-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="4e284-145">Seleccione **Guardar y salir.**</span><span class="sxs-lookup"><span data-stu-id="4e284-145">Select **Save and exit**.</span></span> <span data-ttu-id="4e284-146">Se reiniciará el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e284-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="4e284-147">Usar el archivo SkypeSettings.xml de configuración</span><span class="sxs-lookup"><span data-stu-id="4e284-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="4e284-148">Las siguientes opciones de configuración se pueden agregar al `SkypeSettings.xml` archivo ubicado `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` en.</span><span class="sxs-lookup"><span data-stu-id="4e284-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="4e284-149">Para obtener más información sobre el archivo, consulte Administrar de forma remota una configuración de consola de Salas de `SkypeSettings.xml` Microsoft Teams con un archivo de configuración [XML.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="4e284-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="4e284-150">Para habilitar las reuniones de Cisco WebEx, establezca el `WebExMeetingsEnabled` elemento XML en **"True",** tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="4e284-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="4e284-151">Para habilitar las reuniones de zoom, establezca el `ZoomMeetingsEnabled` elemento XML en **True,** tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="4e284-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="4e284-152">Opcionalmente, puede especificar un nombre de usuario y una dirección de correo electrónico personalizados para unirse a reuniones de terceros con los siguientes elementos XML.</span><span class="sxs-lookup"><span data-stu-id="4e284-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="4e284-153">Si los valores que proporciona no son válidos, el dispositivo salas de Teams usará de forma predeterminada el nombre de usuario y la dirección de correo electrónico del buzón de sala.</span><span class="sxs-lookup"><span data-stu-id="4e284-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="4e284-154">Para unirse a una reunión de Cisco WebEx desde un dispositivo de salas de Teams, la reunión de Cisco debe hospedarse con la versión de aplicación web Cisco WBS 40.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="4e284-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

