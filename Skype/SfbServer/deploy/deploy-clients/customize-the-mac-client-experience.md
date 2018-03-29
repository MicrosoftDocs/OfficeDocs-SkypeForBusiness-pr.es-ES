---
title: Personalizar la experiencia del cliente de Mac en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.
ms.openlocfilehash: 8c779ad35d82b42bc8e162599265f6a25f7a65c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="eb1ca-103">Personalizar la experiencia del cliente de Mac en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="eb1ca-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="eb1ca-104">En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="eb1ca-105">Configuración de las preferencias del cliente de Skype Empresarial en Mac</span><span class="sxs-lookup"><span data-stu-id="eb1ca-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="eb1ca-106">Ciertas características y comportamientos que están disponibles para Skype para el negocio en los clientes de Mac se determinan mediante la configuración de las preferencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="eb1ca-107">El Skype para el negocio en las preferencias de Mac se encuentran en un archivo ubicado en equipos Mac que tiene instalado el Skype para Business client en la siguiente ruta:</span><span class="sxs-lookup"><span data-stu-id="eb1ca-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="eb1ca-108">**~/Library/Containers/com.Microsoft.SkypeForBusiness/Data/Library/Preferences/com.Microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="eb1ca-109">Para establecer estas preferencias, llegar a un mensaje de terminal en Mac del cliente y como sea necesario escribir comandos de clave valores predeterminados escritura com.microsoft.SkypeForBusiness utilizando las teclas de preferencia que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="eb1ca-110">**Claves de preferencia del cliente**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-110">**Client preference keys**</span></span>


|<span data-ttu-id="eb1ca-111">**Clave**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-111">**Key**</span></span>|<span data-ttu-id="eb1ca-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-112">**Type**</span></span>|<span data-ttu-id="eb1ca-113">**Valor**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-113">**Value**</span></span>|<span data-ttu-id="eb1ca-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eb1ca-114">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb1ca-115">AutoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="eb1ca-115">AutoDetectAutoDicoveryURLs</span></span>  <br/> |<span data-ttu-id="eb1ca-116">Booleano</span><span class="sxs-lookup"><span data-stu-id="eb1ca-116">Bool</span></span>  <br/> |<span data-ttu-id="eb1ca-117">0 = configuración manual del servidor</span><span class="sxs-lookup"><span data-stu-id="eb1ca-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="eb1ca-118">1 = detección automática de servidores (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="eb1ca-118">1 = automatic server detection (default)</span></span>  <br/> |<span data-ttu-id="eb1ca-119">Especificar cómo Skype para empresas identifica el transporte y el servidor que se utilizará durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="eb1ca-120">Si habilita esta configuración de directiva, debe especificar **internalAutoDiscoveryURL** y **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span> <br/> |
|<span data-ttu-id="eb1ca-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="eb1ca-121">internalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="eb1ca-122">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-122">String</span></span>  <br/> |<span data-ttu-id="eb1ca-123">URL de detección automática completa</span><span class="sxs-lookup"><span data-stu-id="eb1ca-123">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="eb1ca-124">URL de detección automática interna</span><span class="sxs-lookup"><span data-stu-id="eb1ca-124">Internal autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="eb1ca-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="eb1ca-125">externalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="eb1ca-126">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-126">String</span></span>  <br/> |<span data-ttu-id="eb1ca-127">URL de detección automática completa</span><span class="sxs-lookup"><span data-stu-id="eb1ca-127">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="eb1ca-128">URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="eb1ca-128">External autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="eb1ca-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="eb1ca-129">httpProxyDomain</span></span>  <br/> |<span data-ttu-id="eb1ca-130">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-130">String</span></span>  <br/> ||<span data-ttu-id="eb1ca-131">Dominio de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="eb1ca-131">HTTP Proxy Domain</span></span>  <br/> |
|<span data-ttu-id="eb1ca-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="eb1ca-132">httpProxyUserName</span></span>  <br/> |<span data-ttu-id="eb1ca-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-133">String</span></span>  <br/> ||<span data-ttu-id="eb1ca-134">Nombre de usuario de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="eb1ca-134">HTTP Proxy Username</span></span>  <br/> |
|<span data-ttu-id="eb1ca-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="eb1ca-135">httpProxyPassword</span></span>  <br/> |<span data-ttu-id="eb1ca-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-136">String</span></span>  <br/> ||<span data-ttu-id="eb1ca-137">Contraseña de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="eb1ca-137">HTTP Proxy Password</span></span>  <br/> |
|<span data-ttu-id="eb1ca-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="eb1ca-138">trustedDomainList</span></span>  <br/> |<span data-ttu-id="eb1ca-139">Matriz</span><span class="sxs-lookup"><span data-stu-id="eb1ca-139">Array</span></span>  <br/> ||<span data-ttu-id="eb1ca-140">Lista de dominios de confianza para redireccionamientos HTTP.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-140">List of trusted domains for HTTP redirects.</span></span>  <br/> |
|<span data-ttu-id="eb1ca-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="eb1ca-141">autoAcceptTimeout</span></span>  <br/> |<span data-ttu-id="eb1ca-142">Número</span><span class="sxs-lookup"><span data-stu-id="eb1ca-142">Number</span></span>  <br/> |<span data-ttu-id="eb1ca-143">300 (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="eb1ca-143">300 (default)</span></span>  <br/> |<span data-ttu-id="eb1ca-144">Tiempo de espera de aceptación automática para usuarios sin historial de conversaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>  <br/> |
|<span data-ttu-id="eb1ca-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="eb1ca-145">warnWhenUnknownLocationForE911</span></span>  <br/> |<span data-ttu-id="eb1ca-146">Booleano</span><span class="sxs-lookup"><span data-stu-id="eb1ca-146">Bool</span></span>  <br/> |<span data-ttu-id="eb1ca-147">0 = Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="eb1ca-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="eb1ca-148">1 = Habilitado</span><span class="sxs-lookup"><span data-stu-id="eb1ca-148">1 = Enabled</span></span>  <br/> |<span data-ttu-id="eb1ca-149">Advierte al usuario cuando se marca un número de emergencia desde una ubicación desconocida.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-149">Warns the user when dialing an emergency number from an unknown location.</span></span>  <br/> |
|<span data-ttu-id="eb1ca-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="eb1ca-150">sipAddress</span></span>  <br/> |<span data-ttu-id="eb1ca-151">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-151">String</span></span>  <br/> ||<span data-ttu-id="eb1ca-152">La dirección SIP (correo electrónico) se utiliza para iniciar sesión en Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="eb1ca-153">nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="eb1ca-153">userName</span></span>  <br/> |<span data-ttu-id="eb1ca-154">Cadena</span><span class="sxs-lookup"><span data-stu-id="eb1ca-154">String</span></span>  <br/> ||<span data-ttu-id="eb1ca-155">UPN (UserName) que se utiliza para iniciar sesión en Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="eb1ca-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="eb1ca-156">userNameInAdvancedOnly</span></span>  <br/> |<span data-ttu-id="eb1ca-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="eb1ca-157">Bool</span></span>  <br/> |<span data-ttu-id="eb1ca-158">0 = Mostrar el campo de nombre de usuario en la pantalla de inicio de sesión principal y en el cuadro de diálogo Propiedades avanzadas</span><span class="sxs-lookup"><span data-stu-id="eb1ca-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="eb1ca-159">1 = mostrar el campo de nombre de usuario sólo en el cuadro de diálogo Propiedades avanzadas (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="eb1ca-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>  <br/> |<span data-ttu-id="eb1ca-160">Especificar dónde se muestra el campo nombre de usuario durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-160">Specify where the User Name field is displayed during sign-in.</span></span>  <br/> |
   
### <a name="usage-examples"></a><span data-ttu-id="eb1ca-161">Ejemplos de uso</span><span class="sxs-lookup"><span data-stu-id="eb1ca-161">Usage examples</span></span>

<span data-ttu-id="eb1ca-162">Para agregar un solo dominio (Contoso.com) a la lista de dominios de confianza utilizaría la clave trustedDomainList como se muestra:</span><span class="sxs-lookup"><span data-stu-id="eb1ca-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="eb1ca-163">trustedDomainList de com.microsoft.SkypeForBusiness de escritura de valores predeterminados-matriz-agregar "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="eb1ca-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="eb1ca-164">Para agregar varios dominios a la lista de dominios de confianza, usaría la clave trustedDomainList del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="eb1ca-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="eb1ca-165">trustedDomainList de com.microsoft.SkypeForBusiness de escritura de valores predeterminados-matriz-agregar "abc.com" "test.org" "sfb.com"</span><span class="sxs-lookup"><span data-stu-id="eb1ca-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
<span data-ttu-id="eb1ca-166">Orientación sobre el uso del comando valores predeterminados se puede encontrar en la [biblioteca de referencia de Apple](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/defaults.1.mdl).</span><span class="sxs-lookup"><span data-stu-id="eb1ca-166">Guidance on the use of the defaults command can be found in [Apple's reference library](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/defaults.1.mdl).</span></span> <span data-ttu-id="eb1ca-167">Aunque esta página es antigua y ya no se actualiza, la información que contiene sobre el comando de valores predeterminados no ha cambiado y sigue siendo aplicable.</span><span class="sxs-lookup"><span data-stu-id="eb1ca-167">Although this page is old and no longer maintained, the information about the defaults command is unchanged and still applicable.</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="eb1ca-168">Configuración sin editar de muestra</span><span class="sxs-lookup"><span data-stu-id="eb1ca-168">Sample unedited settings</span></span>

<span data-ttu-id="eb1ca-169">Para que le sirva de referencia, a continuación se muestra una configuración de ejemplo donde se utilizan únicamente los valores predeterminados: </span><span class="sxs-lookup"><span data-stu-id="eb1ca-169">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}

```


