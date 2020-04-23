---
title: Configurar la conectividad híbrida | Implementación de Skype empresarial Server 2019 Connect
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
description: Instrucciones para implementar la conectividad híbrida entre Skype empresarial Server y Skype empresarial online.
ms.openlocfilehash: 0c4b2f716e906e30dd45b2750cfe5487868ce6df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780099"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configuración de la conectividad híbrida entre Skype Empresarial Server y Office 365

**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype empresarial Server y Teams o Skype empresarial online.  La conectividad híbrida permite mover los usuarios locales a Microsoft Teams o Skype empresarial online, y permite a los usuarios aprovechar los servicios en la nube.
  
Antes de llevar a cabo los pasos de este tema, debe tener el plan de lectura de la [Conectividad híbrida entre Skype empresarial Server y Office 365](plan-hybrid-connectivity.md).
  
En la siguiente tabla se enumeran las tareas necesarias para configurar la conectividad híbrida de Skype empresarial y se proporcionan vínculos a los artículos asociados para obtener más información.
  
|Paso|Descripción|
|:-----|:-----|
|Crear una cuenta de inquilino para Office 365   <br/> |Obtenga información sobre Office 365 en [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que su entorno está listo para Office 365, consulte los [requisitos del sistema](https://products.office.com/office-system-requirements).  <br/> Para obtener más información sobre cómo configurar Office 365, vea [Introducción a office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregar su dominio a su organización de Office 365 y comprobar la propiedad  <br/> | Debe agregar el dominio a su organización de Office 365 y, a continuación, seguir los pasos para validar el dominio con Office 365. Esto es para confirmar que es el propietario del dominio. <br/> Para agregar su dominio a su organización de Office 365, siga los pasos descritos en [Agregar un dominio a office 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar la sincronización de Active Directory  <br/> |La sincronización de Active Directory mantiene su Active Directory local sincronizado permanentemente con Office 365. Esto le permite crear versiones sincronizadas de cada grupo y cuenta de usuario.  <br/> <br> **Importante:** Debe sincronizar las cuentas de AD de todos los usuarios de Skype empresarial de su organización entre las implementaciones locales y en línea, incluso si los usuarios no se han movido a teams o Skype empresarial online. Si no sincroniza todos los usuarios, es posible que la comunicación entre los usuarios locales y en línea de su organización no funcione según lo esperado. Para obtener más información, consulte [configurar Azure ad Connect para entornos híbridos](configure-azure-ad-connect.md).         |
| Configurar Skype Empresarial híbrido | Existen tres pasos básicos: <br><br> 1. Configure el entorno local para federar con Office 365. <br> 2. Configure el entorno local para que confíe en Office 365 y habilite el espacio de direcciones SIP compartido con Office 365.<br> 3. habilitar el espacio de direcciones SIP compartido en su organización de Office 365. <br><br> Además, si tiene Exchange local, es posible que quiera configurar OAuth entre los entornos de Exchange local y Skype Empresarial Online. <br> <br>Para obtener más información, consulte [Configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuarios piloto  <br/> |Una vez que haya completado los pasos para preparar y configurar el entorno para Microsoft Teams o Skype empresarial online, puede empezar a mover los usuarios piloto a su organización Office 365 en línea. Para obtener más información, consulte [mover usuarios de local a Skype empresarial online](move-users-from-on-premises-to-skype-for-business-online.md) y [mover usuarios de local a teams](move-users-from-on-premises-to-Teams.md).  <br/> |