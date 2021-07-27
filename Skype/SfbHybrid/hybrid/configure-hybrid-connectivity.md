---
title: Configurar la conectividad híbrida | Implementar Skype Empresarial Server 2019 connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones para implementar la conectividad híbrida entre Skype Empresarial Server y Teams.
ms.openlocfilehash: 832aa989d8f698ac939dbf522476fb9dd6bfb2b8
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574065"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurar la conectividad híbrida entre Skype Empresarial Server y Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype Empresarial Server y Teams.  La conectividad híbrida permite mover a los usuarios locales a Teams y permite a los usuarios aprovechar los servicios en la nube.
  
Antes de realizar los pasos de este tema, debería haber leído [Plan hybrid connectivity between Skype Empresarial Server and Teams](plan-hybrid-connectivity.md).
  
En la tabla siguiente se enumeran las tareas necesarias para configurar Skype Empresarial conectividad híbrida y proporciona vínculos a los artículos asociados para obtener más información.
  
|Paso|Descripción|
|:-----|:-----|
|Crear una cuenta de inquilino para Microsoft 365   <br/> |Obtenga información sobre Microsoft 365 en [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que el entorno está listo para Microsoft 365, consulte [requisitos del sistema](https://products.office.com/office-system-requirements).  <br/> Para obtener más información sobre cómo configurar Microsoft 365, vea [Introducción a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregar el dominio a su Microsoft 365 organización y comprobar la propiedad  <br/> | Debe agregar el dominio a su Microsoft 365 y, a continuación, siga los pasos para validar el dominio con Microsoft 365. Esto es para confirmar que es el propietario del dominio. <br/> Para agregar el dominio a su Microsoft 365 organización, siga los pasos descritos en [Agregar un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar la sincronización de Active Directory  <br/> |La sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Microsoft 365. Esto le permite crear versiones sincronizadas de cada cuenta de usuario y grupo.  <br/> <br> **Importante:** Debes sincronizar las cuentas de AD para todos los usuarios Skype Empresarial de la organización entre las implementaciones locales y en línea, incluso si los usuarios no se mueven a Teams. Si no sincroniza todos los usuarios, es posible que la comunicación entre usuarios locales y en línea de la organización no funcione como se esperaba. Para obtener más información, vea [Configure Azure AD Conectar for hybrid environments](configure-azure-ad-connect.md).         |
| Configurar Skype Empresarial híbrido | Existen tres pasos básicos: <br><br> 1. Configure el entorno local para federar con Microsoft 365. <br> 2. Configure el entorno local para que confíe en Microsoft 365 y habilite el espacio de direcciones SIP compartido con Microsoft 365.<br> 3. Habilite el espacio de direcciones SIP compartido en su Microsoft 365 organización. <br><br> Además, si tiene Exchange local, es posible que desee configurar OAuth entre los entornos Exchange locales y en línea. <br> <br>Para obtener más información, vea [Configure Skype Empresarial hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuarios piloto  <br/> |Después de completar los pasos para preparar y configurar el entorno para Teams, puede empezar a mover usuarios piloto a su organización Microsoft 365 línea. Para obtener más información, vea [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |
