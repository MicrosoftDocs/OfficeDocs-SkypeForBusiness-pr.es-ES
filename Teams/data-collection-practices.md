---
title: Prácticas de recopilación de datos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft recopila datos de error, el uso y el recuento para comprender cómo se utiliza Skype para la empresa y donde los usuarios tienen problemas. Los datos se usan para planear mejoras en los productos.
ms.openlocfilehash: d2673424bcddb1b6b3ebaae3bc7bde7f1fce790f
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464119"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="73fc4-104">Skype para profesionales y Microsoft Teams prácticas de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="73fc4-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="73fc4-105">Skype para Business Server y Skype para profesionales en línea, junto con Skype para las aplicaciones empresariales y de Microsoft Teams, recopilar datos para ayudar a Microsoft a comprender cómo se utilizan estos productos y qué tipos de errores, como errores de inicio de sesión, se han producido.</span><span class="sxs-lookup"><span data-stu-id="73fc4-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="73fc4-106">Esta información nos ayuda a comprender los patrones de uso, planeación de las nuevas características y solucionar problemas y las áreas con problemas.</span><span class="sxs-lookup"><span data-stu-id="73fc4-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="73fc4-107">Mientras que algunos datos de uso se recopilan automáticamente, sólo se puedan recopilar otros datos cuando el usuario o el administrador decide lo permiten.</span><span class="sxs-lookup"><span data-stu-id="73fc4-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="73fc4-108">Recolección de datos entra en estas tres categorías:</span><span class="sxs-lookup"><span data-stu-id="73fc4-108">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="73fc4-109">Datos de recuento</span><span class="sxs-lookup"><span data-stu-id="73fc4-109">Census data</span></span>

- <span data-ttu-id="73fc4-110">Datos de uso</span><span class="sxs-lookup"><span data-stu-id="73fc4-110">Usage data</span></span>

- <span data-ttu-id="73fc4-111">Datos de informes de error</span><span class="sxs-lookup"><span data-stu-id="73fc4-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="73fc4-112">Datos de recuento</span><span class="sxs-lookup"><span data-stu-id="73fc4-112">Census data</span></span>

<span data-ttu-id="73fc4-113">Datos de recuento se adquieren únicamente para proporcionar, el soporte y mejorar Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="73fc4-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="73fc4-114">Los equipos de Microsoft y Skype para la empresa en línea.</span><span class="sxs-lookup"><span data-stu-id="73fc4-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="73fc4-115">Incluye información del entorno, como las versiones de dispositivo y el sistema operativo y la configuración regional y de idioma.</span><span class="sxs-lookup"><span data-stu-id="73fc4-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="73fc4-116">También incluye contadores para los intentos de inicio de sesión y los errores.</span><span class="sxs-lookup"><span data-stu-id="73fc4-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="73fc4-117">Estos son algunos ejemplos específicos de los que se recopilan datos de recuento:</span><span class="sxs-lookup"><span data-stu-id="73fc4-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="73fc4-118">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="73fc4-118">**Data type**</span></span>|<span data-ttu-id="73fc4-119">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="73fc4-119">**Example**</span></span>|<span data-ttu-id="73fc4-120">**Notas**</span><span class="sxs-lookup"><span data-stu-id="73fc4-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73fc4-121">Nombre de aplicación</span><span class="sxs-lookup"><span data-stu-id="73fc4-121">AppName</span></span>  <br/> |<span data-ttu-id="73fc4-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="73fc4-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="73fc4-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="73fc4-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="73fc4-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="73fc4-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="73fc4-125">OSName</span><span class="sxs-lookup"><span data-stu-id="73fc4-125">OSName</span></span>  <br/> |<span data-ttu-id="73fc4-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="73fc4-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="73fc4-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="73fc4-127">OSVersion</span></span>  <br/> |<span data-ttu-id="73fc4-128">8.3</span><span class="sxs-lookup"><span data-stu-id="73fc4-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="73fc4-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="73fc4-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="73fc4-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="73fc4-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="73fc4-131">UserID</span><span class="sxs-lookup"><span data-stu-id="73fc4-131">UserID</span></span>  <br/> |<span data-ttu-id="73fc4-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="73fc4-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="73fc4-133">El identificador es un algoritmo hash dos veces: una vez en el cliente y de nuevo en el servicio de telemetría.</span><span class="sxs-lookup"><span data-stu-id="73fc4-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="73fc4-134">El hash garantiza que el identificador no se puede vincular a un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="73fc4-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="73fc4-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="73fc4-135">DeviceID</span></span>  <br/> |<span data-ttu-id="73fc4-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="73fc4-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="73fc4-137">El identificador de dispositivo es un GUID que tiene una vez generado en el dispositivo y se envía al servicio de telemetría aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="73fc4-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="73fc4-138">Datos de recuento no contienen ninguna información que identifica su organización o a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="73fc4-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="73fc4-139">Vea el [Skype para la declaración de privacidad de negocio](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73fc4-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="73fc4-140">Datos de recuento está activado de forma predeterminada y no se puede desactivar por los administradores o los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="73fc4-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="73fc4-141">Datos de uso</span><span class="sxs-lookup"><span data-stu-id="73fc4-141">Usage data</span></span>

<span data-ttu-id="73fc4-142">Los datos de uso incluyen información como el número de llamadas realizadas, número de mensajes instantáneos enviados o recibidos, número de reuniones se unió a, frecuencia de características que se usan y problemas de estabilidad.</span><span class="sxs-lookup"><span data-stu-id="73fc4-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="73fc4-143">Los datos de uso pueden contener información que identifique a su organización, por ejemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="73fc4-143">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="73fc4-144">Estos son algunos ejemplos específicos de los datos de uso que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="73fc4-144">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="73fc4-145">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="73fc4-145">**Data type**</span></span>|<span data-ttu-id="73fc4-146">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="73fc4-146">**Example**</span></span>|<span data-ttu-id="73fc4-147">**Notas**</span><span class="sxs-lookup"><span data-stu-id="73fc4-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73fc4-148">Mensajes Instantáneos</span><span class="sxs-lookup"><span data-stu-id="73fc4-148">IM Sent</span></span>  <br/> |<span data-ttu-id="73fc4-149">12</span><span class="sxs-lookup"><span data-stu-id="73fc4-149">12</span></span>  <br/> ||
|<span data-ttu-id="73fc4-150">Mensajería instantánea recibido</span><span class="sxs-lookup"><span data-stu-id="73fc4-150">IM Received</span></span>  <br/> |<span data-ttu-id="73fc4-151">5</span><span class="sxs-lookup"><span data-stu-id="73fc4-151">5</span></span>  <br/> ||
|<span data-ttu-id="73fc4-152">Unirse a una reunión (intentos)</span><span class="sxs-lookup"><span data-stu-id="73fc4-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="73fc4-153">5</span><span class="sxs-lookup"><span data-stu-id="73fc4-153">5</span></span>  <br/> ||
|<span data-ttu-id="73fc4-154">Unirse a una reunión (correcto)</span><span class="sxs-lookup"><span data-stu-id="73fc4-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="73fc4-155">4</span><span class="sxs-lookup"><span data-stu-id="73fc4-155">4</span></span>  <br/> ||
|<span data-ttu-id="73fc4-156">Minutos de llamada o reunión</span><span class="sxs-lookup"><span data-stu-id="73fc4-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="73fc4-157">30 minutos</span><span class="sxs-lookup"><span data-stu-id="73fc4-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="73fc4-158">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="73fc4-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="73fc4-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73fc4-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="73fc4-160">Este es el nombre de la organización registrada en Office 365 y se transmite en texto no cifrado, lo que significa que no es confusos.</span><span class="sxs-lookup"><span data-stu-id="73fc4-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="73fc4-161">Datos de uso no contienen ninguna información que identifica a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="73fc4-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="73fc4-162">Recolección de datos está activado de forma predeterminada, pero local Administradores pueden desactivarla utilizando la configuración de directiva de grupo DisableAutomaticSendTracing en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="73fc4-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="73fc4-163">Desactivar esta configuración afecta a todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="73fc4-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="73fc4-164">Para obtener más información, vea [Configurar directivas de arranque de cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="73fc4-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="73fc4-165">Los usuarios finales no se puede activar o desactivar la recolección de datos.</span><span class="sxs-lookup"><span data-stu-id="73fc4-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="73fc4-166">Para la aplicación de las reuniones de Skype y las páginas de web del iniciador de participación, la forma de controlar la telemetría es a través de esta directiva:</span><span class="sxs-lookup"><span data-stu-id="73fc4-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="73fc4-167">Esta directiva el valor predeterminado es false, por lo que la colección de telemetría está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="73fc4-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="73fc4-168">Esta configuración es por grupo y controla todos los usuarios que se conectan con la aplicación de las reuniones de Skype a una reunión hospedada en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="73fc4-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="73fc4-169">Datos de informes de error</span><span class="sxs-lookup"><span data-stu-id="73fc4-169">Error reporting data</span></span>

<span data-ttu-id="73fc4-170">Datos de informes de error puede incluir información sobre el rendimiento y confiabilidad, configuración de dispositivo, calidad de la conexión de red, los códigos de error, registros de errores y excepciones.</span><span class="sxs-lookup"><span data-stu-id="73fc4-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="73fc4-171">Estos son algunos ejemplos específicos de datos que se recopilan de informes de error:</span><span class="sxs-lookup"><span data-stu-id="73fc4-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="73fc4-172">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="73fc4-172">**Data type**</span></span>|<span data-ttu-id="73fc4-173">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="73fc4-173">**Example**</span></span>|<span data-ttu-id="73fc4-174">**Notas**</span><span class="sxs-lookup"><span data-stu-id="73fc4-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73fc4-175">Dirección del mensaje</span><span class="sxs-lookup"><span data-stu-id="73fc4-175">Message direction</span></span>  <br/> |<span data-ttu-id="73fc4-176">Entrante</span><span class="sxs-lookup"><span data-stu-id="73fc4-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="73fc4-177">Estado de la conversación</span><span class="sxs-lookup"><span data-stu-id="73fc4-177">Conversation state</span></span>  <br/> |<span data-ttu-id="73fc4-178">Inactividad</span><span class="sxs-lookup"><span data-stu-id="73fc4-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="73fc4-179">Identificador de subproceso de conversación</span><span class="sxs-lookup"><span data-stu-id="73fc4-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="73fc4-180">AdDO8hsJqilU93hQHC3OZaPR2saEA ==</span><span class="sxs-lookup"><span data-stu-id="73fc4-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="73fc4-181">UserID</span><span class="sxs-lookup"><span data-stu-id="73fc4-181">UserID</span></span>  <br/> |<span data-ttu-id="73fc4-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="73fc4-182">amosmarble</span></span> <br/> |<span data-ttu-id="73fc4-183">El identificador se envía en texto no cifrado, que el servicio de telemetría aplica el algoritmo hash antes de almacenarlos</span><span class="sxs-lookup"><span data-stu-id="73fc4-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="73fc4-184">Datos de informes de error también puede contener información de identificación personal, como la dirección IP y el Session Initiation Protocol Uniform Resource Identifier (URI de SIP) del usuario.</span><span class="sxs-lookup"><span data-stu-id="73fc4-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="73fc4-185">Vea el [Skype para la declaración de privacidad de negocio](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="73fc4-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="73fc4-186">Informes de errores requieren dos cosas:</span><span class="sxs-lookup"><span data-stu-id="73fc4-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="73fc4-187">La configuración de directiva de grupo de DisableAutomaticSendTracing está establecida en False en el servidor o en el centro de administración de inquilinos (es decir, el estado predeterminado).</span><span class="sxs-lookup"><span data-stu-id="73fc4-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="73fc4-188">Para obtener más información, vea [Configurar directivas de arranque de cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .</span><span class="sxs-lookup"><span data-stu-id="73fc4-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="73fc4-189">Los usuarios finales individualmente participar en de la ficha General (haga clic en el icono del engranaje ![icono de engranaje](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) y, a continuación, se abre el cuadro de diálogo **Opciones** con la ficha **General** que se muestra) en el Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="73fc4-189">End users individually opt in from the General tab (click the gear icon ![Gear icon](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Skype para checkbox de colección de datos profesionales en el cuadro de diálogo Opciones > General](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="73fc4-191">Para la aplicación de las reuniones de Skype, la MeetingUxEnableTelemetry controla también informes de errores, aunque para se bloquea en Windows, la configuración de Watson control cargar información de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="73fc4-191">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="73fc4-192">No hay ninguna configuración de usuario para la aplicación de las reuniones de Skype como se puede ver en el cuadro de diálogo de cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="73fc4-192">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="73fc4-193">Para obtener más información, vea [General para establecer opciones de Skype para la empresa](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .</span><span class="sxs-lookup"><span data-stu-id="73fc4-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="73fc4-194">Puede ver [configurar su red para Skype para empresarial en línea](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar la red.</span><span class="sxs-lookup"><span data-stu-id="73fc4-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="73fc4-195">Si usa Office 365 operado por 21Vianet en China, consulte [Configurar la red para Skype para profesionales Online operado por 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="73fc4-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="73fc4-196">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="73fc4-196">Related topics</span></span>
[<span data-ttu-id="73fc4-197">Programa para la mejora de la experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="73fc4-197">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/default.mspx)

[<span data-ttu-id="73fc4-198">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="73fc4-198">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
