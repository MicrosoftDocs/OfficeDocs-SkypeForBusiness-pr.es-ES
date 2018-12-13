---
title: Actualizar AAD conectar para incluir más de un bosque
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye los pasos detallados para la actualización de AAD conectar para incluir más de uno de los bosques como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247735"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="1a4b3-103">Actualizar AAD conectar para incluir más de un bosque</span><span class="sxs-lookup"><span data-stu-id="1a4b3-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="1a4b3-104">Conectar de Azure AD admite la [sincronización de varios bosques](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="1a4b3-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="1a4b3-105">Sin embargo, es compatible con una única instancia de sincronización de Azure Connect de AD con AAD.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="1a4b3-106">Por lo tanto, en los casos donde Azure AD ya está instalado en un bosque, se debe actualizar la instancia existente de AAD conectar a la sincronización desde el bosque adicional.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="1a4b3-107">Si todas las identidades se representan sólo una vez a través de ambos bosques (es decir, que no ha realizado todos los contactos habilitados para correo), a continuación, simplemente vuelva a ejecutar el Asistente para la conexión AAD, elija "Personalizar las opciones de sincronización" y, a continuación, en la \*\*conectar los directorios \*\*página, escriba el nombre del bosque adicional y credenciales.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="1a4b3-108">![El conectar su página de directorios](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="1a4b3-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="1a4b3-109">Sin embargo, si los usuarios pueden existir en más de un directorio y aquí se combinar los datos (por ejemplo, si existen objetos de contacto en un bosque correspondiente a los usuarios en otro bosque), deberá desinstalar Azure Connect AD y volver a instalarlo.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="1a4b3-110">Esto es debido a que la condición de las reglas de combinación de entre bosques sólo se puede configurar durante la primera instalación.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="1a4b3-111">Esto se realiza en la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a4b3-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="1a4b3-112">![Los caracteres que identifica la página de usuarios](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="1a4b3-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="1a4b3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a4b3-113">See also</span></span>

[<span data-ttu-id="1a4b3-114">Consolidación de la nube para equipos y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="1a4b3-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)