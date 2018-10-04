---
title: Migrar teléfonos de área común
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Teléfonos de área común son IP teléfonos que más a menudo residen en un área de trabajo compartida o área común, como una sala de espera, cocinas o fábrica de planta. Teléfonos de área común no es necesario estar conectado a un equipo para proporcionar que Skype para Business Server unificada funcionalidad de comunicaciones unificadas. Después de la migración de una implementación a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Mediante Skype para Shell de administración de servidor empresarial se primero recuperar todos los objetos de contacto asociados con los teléfonos de área común heredado y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
ms.openlocfilehash: d2d30e087d44973379d5f57dd85d137482762e5e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371577"
---
# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

Teléfonos de área común son IP teléfonos que más a menudo residen en un área de trabajo compartida o área común, como una sala de espera, cocinas o fábrica de planta. Teléfonos de área común no es necesario estar conectado a un equipo para proporcionar que Skype para Business Server unificada funcionalidad de comunicaciones unificadas. Después de la migración de una implementación a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Usa Skype para Shell de administración de servidor empresarial, se primero recuperar todos los objetos de contacto asociados con los teléfonos de área común heredado y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

1. De Skype para servidor Front-End de Business Server 2019, abra Skype para Shell de administración de servidor empresarial.
    
2. Desde la línea de comandos, escriba lo siguiente:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para comprobar que todos los objetos de contacto se han movido a la Skype para el grupo de servidores de Business Server 2019, desde el Skype para Shell de administración de servidor empresarial escriba lo siguiente:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Compruebe que todos los objetos de contacto están ahora asociadas con el Skype para el grupo de servidores de Business Server 2019.
    

