---
title: Actualizar el certificado de servidor perimetral
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
description: Este apéndice incluye los pasos detallados para actualizar el certificado de servidor perimetral como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247726"
---
# <a name="update-the-edge-certificate"></a>Actualizar el certificado de servidor perimetral

Actualizar el certificado de servidor perimetral es el paso clave para asegurarse de que un entorno en prem con SipDomain1 puede unirse a un entorno de nube con SipDomain2 y garantizar el enrutamiento adecuado en un entorno de espacio de direcciones compartida entre los dos dominios SIP. Consulte el paso 14 de [consolidación en la nube para equipos y Skype para la empresa](cloud-consolidation.md) para el contexto en el que es posible que realice este paso. En los ejemplos, SipDomain1 es AcquiredCompany. <span>com y SipDomain2 es OriginalCompany. <span>com.

El nombre alternativo de sujeto (SAN) del certificado en todos los servidores perimetrales en el entorno local debe actualizarse para incluir todos los dominios SIP que existen en el inquilino online puro (excluyendo cualquier onmicrosoft.<span> dominios de COM), con el formato "sip. \<dominio > ".  En nuestro ejemplo, esto es sip. OriginalCompany. <span>com. Este paso es fundamental para hacer antes de migrar los usuarios a la nube.

**Pasos siguientes:**

1.  Obtener un nuevo certificado de perímetro externo para el borde que tiene todas las entradas más entradas adicionales en el SAN para todos los dominios SIP en el entorno de nube (excluyendo *. onmicrosoft.com dominios) con el formato "sip. <DomainName>".
2.  Instale el certificado localmente en cada servidor perimetral y asignar al servicio perimetral de Skype en cada uno de los servicio perimetral.  Para obtener instrucciones detalladas, consulte la sección "Certificados de interfaz de perímetro externo" en [Implementar servicio perimetral en Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Reinicie el servicio perimetral en cada uno de los servidores perimetrales. Puede hacer esto para un cuadro único con los siguientes comandos de PowerShell:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vea también

[Consolidación de la nube para equipos y Skype para la empresa](cloud-consolidation.md)