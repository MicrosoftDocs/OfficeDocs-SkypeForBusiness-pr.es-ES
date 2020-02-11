---
title: Actualizar el certificado perimetral
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
description: Este apéndice incluye pasos detallados para actualizar el certificado perimetral como parte de la consolidación en la nube para Teams y Skype empresarial.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888609"
---
# <a name="update-the-edge-certificate"></a>Actualizar el certificado perimetral

La actualización del certificado perimetral es el paso clave para garantizar que un entorno local con SipDomain1 puede unirse a un entorno en la nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartido entre los dos dominios SIP. Vea el paso 14 de [consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md) para el contexto en el que puede realizar este paso. En los ejemplos, SipDomain1 es AcquiredCompany. <span>com y SipDomain2 es OriginalCompany. <span>com.

El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales en el entorno local debe actualizarse para incluir todos los dominios SIP que existen en el espacio empresarial en línea puro (excepto cualquier<span> objeto de Microsoft. los dominios com), con el formato "SIP. \<> de dominio ".  En nuestro ejemplo, es SIP. OriginalCompany. <span>com. Es fundamental realizar este paso antes de migrar los usuarios a la nube.

**Acciones**

1.  Obtenga un nuevo certificado perimetral externo para el servidor perimetral que tiene todas las entradas existentes además de entradas adicionales en el SAN para todos los dominios SIP en el entorno de la nube (excluyendo los dominios *. onmicrosoft.com) con el formato "SIP. <DomainName>".
2.  Instale el certificado de forma local en cada servidor perimetral y asígnelo al servicio perimetral de Skype en cada uno de los servicios perimetrales.  Para conocer los pasos detallados, consulte la sección "certificados de la interfaz perimetral externa" en [deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Reinicie el servicio perimetral en cada uno de los servidores perimetrales. Puede hacerlo para un único cuadro con los siguientes comandos de PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vea también

[Consolidación en la nube para Teams y Skype empresarial](cloud-consolidation.md)