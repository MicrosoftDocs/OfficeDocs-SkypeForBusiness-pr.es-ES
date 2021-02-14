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
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888609"
---
# <a name="update-the-edge-certificate"></a>Actualizar el certificado de límite

Actualizar el certificado perimetral es el paso clave para garantizar que un entorno local con SipDomain1 pueda unirse a un entorno de nube con SipDomain2 y garantizar un enrutamiento correcto en un entorno de espacio de direcciones compartido en los dos dominios SIP. Vea el paso 14 en [la consolidación](cloud-consolidation.md) de la nube para Teams y Skype Empresarial para el contexto en el que puede realizar este paso. En nuestros ejemplos, SipDomain1 es AcquiredCompany. <span> com y SipDomain2 es OriginalCompany. <span> com.

El nombre alternativo del firmante (SAN) del certificado en todos los servidores perimetrales del entorno local debe actualizarse para incluir todos los dominios SIP que existen en el espacio empresarial en línea puro (excluyendo cualquier onmicrosoft. <span> com domains), con el formato "sip. \< dominio>".  En nuestro ejemplo, este es sip. OriginalCompany. <span> com. Este paso es fundamental antes de migrar cualquier usuario a la nube.

**Pasos:**

1.  Obtenga un nuevo certificado perimetral externo para el perímetro que tiene todas las entradas existentes más entradas adicionales en el SAN para todos los dominios SIP del entorno de nube (excluidos los dominios *.onmicrosoft.com) con el formato <DomainName> "sip".
2.  Instale el certificado localmente en cada servidor perimetral y asígnelo al servicio perimetral de Skype en cada uno de los servicios perimetrales.  Para conocer los pasos detallados, consulte la sección "Certificados de interfaz perimetral externa" en Implementar el servicio perimetral en [Skype Empresarial Server 2015.](https://technet.microsoft.com/library/dn951368.aspx)
3.  Reinicie el servicio perimetral en cada uno de los servidores perimetrales. Puede hacerlo para un solo cuadro con los siguientes comandos de PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vea también

[Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md)