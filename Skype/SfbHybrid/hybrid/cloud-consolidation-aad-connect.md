---
title: Actualizar AAD Connect para incluir más de un bosque
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para actualizar AAD Connect para incluir más de un bosque como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696065"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="cf1f6-103">Actualizar AAD Connect para incluir más de un bosque</span><span class="sxs-lookup"><span data-stu-id="cf1f6-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="cf1f6-104">Azure AD Connect admite la [sincronización desde varios bosques](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="cf1f6-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="cf1f6-105">Sin embargo, solo admite una instancia de Azure AD Connect que se sincronice con AAD.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="cf1f6-106">Por lo tanto, en los casos donde Azure AD ya está instalado en un bosque, la instancia existente de AAD Connect debe actualizarse para sincronizarse desde el bosque adicional.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="cf1f6-107">Si todas las identidades se representan solo una vez en ambos bosques (es decir, no ha realizado ningún contacto habilitado para correo), simplemente puede volver a ejecutar el Asistente para la conexión de AAD, elegir "personalizar las opciones de sincronización" y, a continuación, en la página **conectar los directorios** , escriba el nombre del bosque y las credenciales adicionales.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="cf1f6-108">![La página conectar los directorios](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="cf1f6-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="cf1f6-109">Sin embargo, si los usuarios pueden existir en más de un directorio y va a combinar los datos (por ejemplo, si existen objetos de contacto en un bosque correspondiente a los usuarios de otro bosque), tendrá que desinstalar Azure AD Connect y volver a instalarlo.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="cf1f6-110">Esto se debe a que la condición reglas de combinación entre bosques solo se puede configurar durante la primera instalación.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="cf1f6-111">Esto se realiza en la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1f6-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="cf1f6-112">![La página identificación de forma exclusiva de usuarios](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="cf1f6-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="cf1f6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf1f6-113">See also</span></span>

[<span data-ttu-id="cf1f6-114">Consolidación en la nube para Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="cf1f6-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)