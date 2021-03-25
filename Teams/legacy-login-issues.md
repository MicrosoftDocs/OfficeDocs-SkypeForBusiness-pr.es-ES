---
title: Problemas al recibir mensajes y llamadas en sistemas heredados en Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Solucionar problemas relacionados con la recepción de mensajes y llamadas en sistemas heredados
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120611"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="65446-103">Problemas al recibir mensajes y llamadas en sistemas heredados</span><span class="sxs-lookup"><span data-stu-id="65446-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="65446-104">Es posible que los usuarios tengan problemas para recibir mensajes o llamadas si usan versiones anteriores de Teams o han iniciado sesión con otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="65446-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="65446-105">Configuraciones de ADU heredadas</span><span class="sxs-lookup"><span data-stu-id="65446-105">Legacy ADU setups</span></span>

 <span data-ttu-id="65446-106">Si los usuarios han iniciado sesión en un equipo unido a un dominio y **no quieren que su nombre de usuario se rellene previamente en la pantalla de inicio de sesión de Teams**, los administradores pueden configurar el registro de Windows siguiente para desactivar el rellenado previo del nombre de usuario (UPN):</span><span class="sxs-lookup"><span data-stu-id="65446-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="65446-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="65446-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="65446-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="65446-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="65446-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="65446-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="65446-110">La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.</span><span class="sxs-lookup"><span data-stu-id="65446-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="65446-111">Vea [Iniciar sesión en Microsoft Teams con autenticación moderna](sign-in-teams.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="65446-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="65446-112">Revocación de tokens de Skype</span><span class="sxs-lookup"><span data-stu-id="65446-112">Skype token revocation</span></span>

<span data-ttu-id="65446-113">Al cambiar o restablecer una contraseña, los clientes antiguos no recibirán mensajes y llamadas durante un máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="65446-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="65446-114">Para resolver este problema, reinicie la aplicación o pase a clientes más recientes.</span><span class="sxs-lookup"><span data-stu-id="65446-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="65446-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="65446-115">Related topics</span></span>

[<span data-ttu-id="65446-116">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="65446-116">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)