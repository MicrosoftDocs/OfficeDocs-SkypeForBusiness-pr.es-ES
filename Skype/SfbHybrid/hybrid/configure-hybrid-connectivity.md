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
ms.openlocfilehash: 2b0e9aabbe029dd292afabf3b7cac579f1029384
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510551"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurar la conectividad híbrida entre Skype Empresarial Server y Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype Empresarial Server y Teams (o Skype Empresarial Online hasta su retirada).  La conectividad híbrida permite mover los usuarios locales a Teams (o Skype Empresarial Online) y permite a los usuarios aprovechar los servicios en la nube.
  
Antes de realizar los pasos de este tema, debería haber leído [Plan hybrid connectivity between Skype Empresarial Server and Teams](plan-hybrid-connectivity.md).
  
En la tabla siguiente se enumeran las tareas necesarias para configurar Skype Empresarial conectividad híbrida y proporciona vínculos a los artículos asociados para obtener más información.
  
|Paso|Descripción|
|:-----|:-----|
|Crear una cuenta de inquilino para Microsoft 365   <br/> |Obtenga información sobre Microsoft 365 en [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que el entorno está listo para Microsoft 365, consulte [requisitos del sistema](https://products.office.com/office-system-requirements).  <br/> Para obtener más información sobre cómo configurar Microsoft 365, vea [Introducción a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregar el dominio a su Microsoft 365 organización y comprobar la propiedad  <br/> | Debe agregar el dominio a su Microsoft 365 y, a continuación, siga los pasos para validar el dominio con Microsoft 365. Esto es para confirmar que es el propietario del dominio. <br/> Para agregar el dominio a su Microsoft 365 organización, siga los pasos descritos en [Agregar un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar la sincronización de Active Directory  <br/> |La sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Microsoft 365. Esto le permite crear versiones sincronizadas de cada cuenta de usuario y grupo.  <br/> <br> **Importante:** Debes sincronizar las cuentas de AD para todos los usuarios de Skype Empresarial de la organización entre las implementaciones locales y en línea, incluso si los usuarios no se mueven a Teams (o Skype Empresarial Online). Si no sincroniza todos los usuarios, es posible que la comunicación entre usuarios locales y en línea de la organización no funcione como se esperaba. Para obtener más información, vea [Configure Azure AD Conectar for hybrid environments](configure-azure-ad-connect.md).         |
| Configurar Skype Empresarial híbrido | Existen tres pasos básicos: <br><br> 1. Configure el entorno local para federar con Microsoft 365. <br> 2. Configure el entorno local para que confíe en Microsoft 365 y habilite el espacio de direcciones SIP compartido con Microsoft 365.<br> 3. Habilite el espacio de direcciones SIP compartido en su Microsoft 365 organización. <br><br> Además, si tiene Exchange local, es posible que quiera configurar OAuth entre los entornos de Exchange local y Skype Empresarial Online. <br> <br>Para obtener más información, vea [Configure Skype Empresarial hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuarios piloto  <br/> |Después de completar los pasos para preparar y configurar el entorno para Teams (o Skype Empresarial Online), puede empezar a mover usuarios piloto a su organización Microsoft 365 línea. Para obtener más información, vea [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md) and Move users from on premises to Skype Empresarial [Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
