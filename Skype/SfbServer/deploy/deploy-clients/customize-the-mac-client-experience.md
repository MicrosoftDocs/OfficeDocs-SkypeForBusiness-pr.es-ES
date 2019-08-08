---
title: Personalizar la experiencia del cliente de Mac en Skype Empresarial
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.
ms.openlocfilehash: 6b343c076d0fd1736cc6974a5c33103f0b6dfcda
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234193"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="f5de8-103">Personalizar la experiencia del cliente de Mac en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f5de8-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="f5de8-104">En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5de8-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="f5de8-105">Configuración de las preferencias del cliente de Skype Empresarial en Mac</span><span class="sxs-lookup"><span data-stu-id="f5de8-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="f5de8-106">Algunas características y comportamientos que están disponibles para clientes de Skype empresarial en Mac están determinados por la configuración de preferencias en el cliente.</span><span class="sxs-lookup"><span data-stu-id="f5de8-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="f5de8-107">Las preferencias de Skype empresarial para Mac se encuentran en un archivo que se encuentra en equipos Mac que han instalado el cliente de Skype empresarial ubicado en la siguiente ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="f5de8-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="f5de8-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="f5de8-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="f5de8-109">Para establecer estas preferencias, vaya a un aviso de terminal en el equipo Mac del cliente y, según sea necesario, Introduzca valores predeterminados escriba los comandos de las teclas com. Microsoft. SkypeForBusiness con las teclas de preferencias que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5de8-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="f5de8-110">**Claves de preferencia de cliente**</span><span class="sxs-lookup"><span data-stu-id="f5de8-110">**Client preference keys**</span></span>


| <span data-ttu-id="f5de8-111">Clave</span><span class="sxs-lookup"><span data-stu-id="f5de8-111">Key</span></span> | <span data-ttu-id="f5de8-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="f5de8-112">Type</span></span> | <span data-ttu-id="f5de8-113">Valor</span><span class="sxs-lookup"><span data-stu-id="f5de8-113">Value</span></span> | <span data-ttu-id="f5de8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5de8-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5de8-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="f5de8-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="f5de8-116">Booleano</span><span class="sxs-lookup"><span data-stu-id="f5de8-116">Bool</span></span>    |<span data-ttu-id="f5de8-117">0 = configuración manual del servidor</span><span class="sxs-lookup"><span data-stu-id="f5de8-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="f5de8-118">1 = detección automática de servidores (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f5de8-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="f5de8-119">Especifique cómo debe identificar Skype empresarial el transporte y el servidor que se van a usar durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f5de8-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="f5de8-120">Si habilita esta configuración de directiva, debe especificar **internalAutoDiscoveryURL** y **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="f5de8-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="f5de8-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="f5de8-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="f5de8-122">String</span><span class="sxs-lookup"><span data-stu-id="f5de8-122">String</span></span>    |<span data-ttu-id="f5de8-123">URL de detección automática completa</span><span class="sxs-lookup"><span data-stu-id="f5de8-123">Full autodiscover URL</span></span>    |<span data-ttu-id="f5de8-124">URL de detección automática interna</span><span class="sxs-lookup"><span data-stu-id="f5de8-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="f5de8-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="f5de8-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="f5de8-126">String</span><span class="sxs-lookup"><span data-stu-id="f5de8-126">String</span></span>    |<span data-ttu-id="f5de8-127">URL de detección automática completa</span><span class="sxs-lookup"><span data-stu-id="f5de8-127">Full autodiscover URL</span></span>    |<span data-ttu-id="f5de8-128">URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="f5de8-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="f5de8-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="f5de8-129">httpProxyDomain</span></span>    |<span data-ttu-id="f5de8-130">String</span><span class="sxs-lookup"><span data-stu-id="f5de8-130">String</span></span>    ||<span data-ttu-id="f5de8-131">Dominio de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="f5de8-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="f5de8-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="f5de8-132">httpProxyUserName</span></span>    |<span data-ttu-id="f5de8-133">String</span><span class="sxs-lookup"><span data-stu-id="f5de8-133">String</span></span>    ||<span data-ttu-id="f5de8-134">Nombre de usuario de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="f5de8-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="f5de8-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="f5de8-135">httpProxyPassword</span></span>    |<span data-ttu-id="f5de8-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="f5de8-136">String</span></span>    ||<span data-ttu-id="f5de8-137">Contraseña de proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="f5de8-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="f5de8-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="f5de8-138">trustedDomainList</span></span>    |<span data-ttu-id="f5de8-139">Matriz</span><span class="sxs-lookup"><span data-stu-id="f5de8-139">Array</span></span>    ||<span data-ttu-id="f5de8-140">Lista de dominios de confianza para redireccionamientos HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5de8-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="f5de8-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="f5de8-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="f5de8-142">Número</span><span class="sxs-lookup"><span data-stu-id="f5de8-142">Number</span></span>    |<span data-ttu-id="f5de8-143">300 (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f5de8-143">300 (default)</span></span>    |<span data-ttu-id="f5de8-144">Tiempo de espera de aceptación automática para usuarios sin historial de conversaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="f5de8-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="f5de8-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="f5de8-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="f5de8-146">Booleano</span><span class="sxs-lookup"><span data-stu-id="f5de8-146">Bool</span></span>    |<span data-ttu-id="f5de8-147">0 = Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f5de8-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="f5de8-148">1 = Habilitado</span><span class="sxs-lookup"><span data-stu-id="f5de8-148">1 = Enabled</span></span>    |<span data-ttu-id="f5de8-149">Advierte al usuario cuando se marca un número de emergencia desde una ubicación desconocida.</span><span class="sxs-lookup"><span data-stu-id="f5de8-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="f5de8-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="f5de8-150">sipAddress</span></span>    |<span data-ttu-id="f5de8-151">String</span><span class="sxs-lookup"><span data-stu-id="f5de8-151">String</span></span>    ||<span data-ttu-id="f5de8-152">Dirección SIP (correo electrónico) usada para iniciar sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5de8-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="f5de8-153">userName</span><span class="sxs-lookup"><span data-stu-id="f5de8-153">userName</span></span>    |<span data-ttu-id="f5de8-154">Cadena</span><span class="sxs-lookup"><span data-stu-id="f5de8-154">String</span></span>    ||<span data-ttu-id="f5de8-155">El UPN (nombre de usuario) usado para iniciar sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5de8-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="f5de8-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="f5de8-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="f5de8-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="f5de8-157">Bool</span></span>    |<span data-ttu-id="f5de8-158">0 = mostrar el campo Nombre de usuario en la pantalla de inicio de sesión principal y en el cuadro de diálogo Propiedades avanzadas.</span><span class="sxs-lookup"><span data-stu-id="f5de8-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="f5de8-159">1 = Mostrar el campo Nombre de usuario solo en el cuadro de diálogo Propiedades avanzadas (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f5de8-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="f5de8-160">Especifique dónde se muestra el campo Nombre de usuario durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f5de8-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="f5de8-161">Ejemplos de uso</span><span class="sxs-lookup"><span data-stu-id="f5de8-161">Usage examples</span></span>

<span data-ttu-id="f5de8-162">Para agregar un solo dominio (Contoso.com) a la lista de dominios de confianza, usaría la clave trustedDomainList, tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f5de8-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="f5de8-163">los valores predeterminados escriben com. Microsoft. SkypeForBusiness trustedDomainList-array-Add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="f5de8-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="f5de8-164">Para agregar varios dominios a la lista de dominios de confianza, usaría la clave trustedDomainList del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="f5de8-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="f5de8-165">los valores predeterminados escriben com. Microsoft. SkypeForBusiness trustedDomainList-array-Add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="f5de8-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="f5de8-166">Configuración sin editar de muestra</span><span class="sxs-lookup"><span data-stu-id="f5de8-166">Sample unedited settings</span></span>

<span data-ttu-id="f5de8-167">Para que le sirva de referencia, a continuación se muestra una configuración de ejemplo donde se utilizan únicamente los valores predeterminados: </span><span class="sxs-lookup"><span data-stu-id="f5de8-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
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
