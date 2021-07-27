---
title: Actualizar el certificado de límite
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
description: Este apéndice incluye pasos detallados para actualizar el certificado perimetral como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: aa360d1c481b2a05b1282ca7538e5cf7b8f8de71
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510421"
---
# <a name="update-the-edge-certificate"></a>Actualizar el certificado de límite

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Actualizar el certificado perimetral es el paso clave para garantizar que un entorno local con SipDomain1 pueda unirse a un entorno de nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartido en los dos dominios SIP. Vea el paso 14 en [Consolidación](cloud-consolidation.md) de la nube Teams y Skype Empresarial para obtener contexto en el que puede realizar este paso. En nuestros ejemplos, SipDomain1 es AcquiredCompany. <span> com y SipDomain2 es OriginalCompany. <span> com.

El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales del entorno local debe actualizarse para incluir todos los dominios SIP que existen en el espacio empresarial en línea puro (excluyendo cualquier onmicrosoft. <span> dominios com), con el formato "sip. \<domain> ".  En nuestro ejemplo, se trata de sip. OriginalCompany. <span> com. Este paso es fundamental antes de migrar cualquier usuario a la nube.

**Pasos:**

1.  Obtenga un nuevo certificado perimetral externo para el servidor perimetral que tenga todas las entradas existentes más entradas adicionales en el SAN para todos los dominios SIP del entorno de nube (excluyendo los dominios *.onmicrosoft.com) con el formato <DomainName> "sip.".
2.  Instale el certificado localmente en cada servidor perimetral y asígnelo al servicio perimetral Skype en cada uno de los servicios perimetrales.  Para obtener pasos detallados, vea la sección "Certificados de interfaz perimetral externa" en [Deploy Edge Service in Skype Empresarial Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Reinicie el servicio perimetral en cada uno de los servidores perimetrales. Puede hacerlo en un solo cuadro con los siguientes comandos de PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vea también

[Consolidación de nube para Teams y Skype Empresarial](cloud-consolidation.md)