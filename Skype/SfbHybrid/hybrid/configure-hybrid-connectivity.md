---
title: Configurar la conectividad híbrida | Implementar la conexión de Skype Empresarial Server 2019
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
description: Instrucciones para implementar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376753"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configuración de la conectividad híbrida entre Skype Empresarial Server y Office 365

**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype Empresarial Server y Teams o Skype Empresarial Online.  La conectividad híbrida permite mover los usuarios locales a Teams o Skype Empresarial Online, y permite a los usuarios aprovechar los servicios en la nube.
  
Antes de realizar los pasos de este tema, debe haber leído [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md).
  
En la tabla siguiente se enumeran las tareas necesarias para configurar la conectividad híbrida de Skype Empresarial y se proporcionan vínculos a los artículos asociados para obtener más información.
  
|Paso|Descripción|
|:-----|:-----|
|Crear una cuenta de inquilino para Office 365   <br/> |Obtenga información sobre Office 365 en [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Para asegurarse de que su entorno está listo para Office 365, vea los [requisitos del sistema.](https://products.office.com/office-system-requirements)  <br/> Para obtener más información sobre cómo configurar Office 365, consulte [Introducción a Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|Agregar el dominio a la organización de Office 365 y comprobar la propiedad  <br/> | Debe agregar su dominio a su organización de Office 365 y, a continuación, siga los pasos para validar el dominio con Office 365. Esto es para confirmar que es el propietario del dominio. <br/> Para agregar su dominio a su organización de Office 365, siga los pasos descritos en Agregar un dominio [a Office 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Configurar la sincronización de Active Directory  <br/> |La sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Office 365. Esto le permite crear versiones sincronizadas de cada cuenta de usuario y grupo.  <br/> <br> **Importante:** Debe sincronizar las cuentas de AD para todos los usuarios de Skype Empresarial de su organización entre las implementaciones locales y en línea, incluso si los usuarios no se mueven a Teams o Skype Empresarial Online. Si no sincroniza todos los usuarios, es posible que la comunicación entre los usuarios locales y en línea de su organización no funcione según lo esperado. Para obtener más información, vea [Configurar Azure AD Connect para entornos híbridos.](configure-azure-ad-connect.md)         |
| Configurar Skype Empresarial híbrido | Existen tres pasos básicos: <br><br> 1. Configure el entorno local para federar con Office 365. <br> 2. Configure su entorno local para que confíe en Office 365 y habilite el espacio de direcciones SIP compartido con Office 365.<br> 3. Habilite el espacio de direcciones SIP compartido en su organización de Office 365. <br><br> Además, si tiene Exchange local, es posible que quiera configurar OAuth entre los entornos de Exchange local y Skype Empresarial Online. <br> <br>Para obtener más información, consulte [Configurar Skype Empresarial híbrido.](configure-federation-with-skype-for-business-online.md)
|Mover usuarios piloto  <br/> |Después de completar los pasos para preparar y configurar su entorno para Teams o Skype Empresarial Online, puede empezar a mover usuarios piloto a su organización de Office 365 en línea. Para obtener más información, vea [Mover usuarios locales a Skype](move-users-from-on-premises-to-skype-for-business-online.md) Empresarial Online y Mover usuarios de local a [Teams.](move-users-from-on-premises-to-Teams.md)  <br/> |
