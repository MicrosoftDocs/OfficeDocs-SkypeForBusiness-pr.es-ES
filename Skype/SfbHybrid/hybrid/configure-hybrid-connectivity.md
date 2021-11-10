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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Instrucciones para implementar la conectividad híbrida entre Skype Empresarial Server y Teams.
ms.openlocfilehash: ffc1205ca91f81e9b9361e4603318bc1a8fcf76c
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887178"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurar la conectividad híbrida entre Skype Empresarial Server y Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype Empresarial Server y Teams.  La conectividad híbrida permite mover a los usuarios locales a Teams y permite a los usuarios aprovechar los servicios en la nube.
  
Antes de realizar los pasos de este tema, debería haber leído [Plan hybrid connectivity between Skype Empresarial Server and Teams](plan-hybrid-connectivity.md).
  
En la tabla siguiente se enumeran las tareas necesarias para configurar Skype Empresarial conectividad híbrida y proporciona vínculos a los artículos asociados para obtener más información.
  
|Paso|Descripción|
|:-----|:-----|
|Crear una cuenta de espacio empresarial para Microsoft 365.   <br/> |Obtenga información sobre Microsoft 365 en [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que el entorno está listo para Microsoft 365, consulte [requisitos del sistema](https://products.office.com/office-system-requirements).  <br/> Para obtener más información sobre cómo configurar Microsoft 365, vea [Introducción a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregue el dominio a su Microsoft 365 organización y compruebe la propiedad.  <br/> | Debe agregar el dominio a su Microsoft 365 y, a continuación, siga los pasos para validar el dominio con Microsoft 365. Esta validación es para confirmar que es el propietario del dominio. <br/> Para agregar el dominio a su Microsoft 365 organización, siga los pasos descritos en [Agregar un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US). Asegúrese de revisar las instrucciones que se indican a continuación sobre las [implicaciones de DNS para las organizaciones que se convierten en híbridas](#dns-implications-for-on-premises-organizations-that-become-hybrid). <br/> |
|Configurar la sincronización de Active Directory.  <br/> |La sincronización de Active Directory garantiza que active directory local se sincronice continuamente con Microsoft 365 para crear versiones sincronizadas de cada cuenta de usuario y grupo.  <br/> <br> **Importante:** Debe sincronizar las cuentas de Active Directory para todos los usuarios de Skype Empresarial de la organización entre las implementaciones locales y en línea, incluso si los usuarios no se mueven a Teams. Si no sincroniza todos los usuarios, es posible que la comunicación entre usuarios locales y en línea de la organización no funcione como se esperaba. Para obtener más información, vea [Configure Azure AD Conectar for hybrid environments](configure-azure-ad-connect.md).         |
| Configurar Skype Empresarial híbrido | Existen tres pasos básicos: <br><br> 1. Configure el entorno local para federar con Microsoft 365. <br> 2. Configure el entorno local para que confíe en Microsoft 365 y habilite el espacio de direcciones SIP compartido con Microsoft 365.<br> 3. Habilite el espacio de direcciones SIP compartido en su Microsoft 365 organización. <br><br> Además, si tiene Exchange local, es posible que desee configurar OAuth entre los entornos Exchange locales y en línea. <br> <br>Para obtener más información, vea [Configure Skype Empresarial hybrid](configure-federation-with-skype-for-business-online.md).
|Mover los usuarios piloto  <br/> |Después de completar los pasos para preparar y configurar el entorno para Teams, puede empezar a mover usuarios piloto a su organización Microsoft 365 línea. Para obtener más información, vea [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>Implicaciones de DNS para organizaciones locales que se convierten en híbridas

De forma predeterminada, los inquilinos se crean como modo TeamsOnly. Los administradores no pueden cambiar esta configuración. Sin embargo, las organizaciones híbridas no deben ser el modo TeamsOnly porque esto rompería la federación para sus usuarios locales. Teams tiene un mecanismo integrado para asegurarse de que la configuración de TeamsOnly en todo el espacio empresarial no se aplica a los nuevos inquilinos híbridos, y también que la configuración de TeamsOnly de todo el espacio empresarial se quita de los *inquilinos existentes* que se convierten en híbridos. Este mecanismo se basa en el valor del registro DNS de LyncDiscover para cualquier dominio Microsoft 365 comprobado (porque una implementación local de Skype Empresarial Server en la mayoría de los casos tendrá ese registro), como se describe a continuación.

Cuando se procesa una Microsoft 365 suscripción nueva, se produce lo siguiente:
- Si aún no hay ningún dominio Microsoft 365, el espacio empresarial se crea como modo TeamsOnly. El valor se establece a través de TeamsUpgradeOverridePolicy, que solo microsoft puede establecer. Si el valor de la directiva es UpgradeToTeams, tiene prioridad sobre cualquier valor de TeamsUpgradePolicy.
- Si hay dominios Microsoft 365 comprobados, pero no se han detectado registros de LyncDiscover de DNS públicos, o si algún registro LyncDiscover detectado apunta Microsoft 365 (sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us, etc.), el inquilino se crea como modo TeamsOnly (a través de TeamsUpgradeOverridePolicy).
- Si hay al menos un dominio Microsoft 365 comprobado para el que se detecta un registro lyncdiscover y ese registro apunta a otro lugar que no sea Microsoft 365, el espacio empresarial se crea como modo Islas.

Cuando se vuelve a aprovisionar un espacio empresarial Microsoft 365 existente (normalmente debido a un cambio en dominios comprobados o en detalles de suscripción), se produce lo siguiente:
- Si se encuentra un registro de LyncDiscover para uno o varios de los dominios comprobados de Microsoft 365 y ese registro no apunta Microsoft 365, se quita el modo TeamsOnly de todo el espacio empresarial (a través de TeamsUpgradeOverridePolicy). El modo de inquilino revertirá a lo que se especifique en el nivel de inquilino para TeamsUpgradePolicy, que, de forma predeterminada, es el modo Islas.


Existen algunas limitaciones para este mecanismo de detección automática:
- Si su organización no tiene registros DNS públicos, el modo TeamsOnly no se quitará ya que Microsoft 365 no podrá detectar los registros. Si su organización tiene una Skype Empresarial Server local sin entradas DNS públicas, tendrá que ponerse en contacto con el Soporte técnico de Microsoft para que el espacio empresarial se haya degradado.
- Si agrega o actualiza un registro DNS  público a un dominio que ya es un dominio Microsoft 365 comprobado, este cambio dns no se detecta y el modo TeamsOnly no se quitará. El modo TeamsOnly solo se quita si se vuelve a aprovisionar el espacio empresarial, lo que suele ocurrir cuando se produce un cambio en Microsoft 365 dominios comprobados o en la suscripción.  
