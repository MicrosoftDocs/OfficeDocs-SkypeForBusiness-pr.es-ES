---
title: Dar soporte para trabajadores remotos con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: Use estas recomendaciones para ayudar a los trabajadores remotos de su organización a ser productivos con Microsoft Teams, especialmente cuando trabajan desde casa (WFH) en respuesta al ataque COVID-19 (coronavirus).
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374317"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Dar soporte para trabajadores remotos con Microsoft Teams

Use los procedimientos recomendados de este artículo para dar soporte a los usuarios que trabajan de forma remota o desde casa

## <a name="technical"></a>Técnico

1.  Asegúrese de que [Teams está activado para todos los usuarios](assign-teams-licenses.md)
    
      - Vea [Teams Exploratory](e1-trial-license.md), [Teams E1 Prueba](teams-exploratory.md) o [Teams gratuito](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) para asegurarse de que todos los usuarios de su empresa tengan acceso a él.

      - Los empleados que están en lugares remotos confían mucho en las reuniones y en las conferencias de audio. Si aún no ha implementado estas cargas de trabajo, vea[ las reuniones y conferencias en Teams](deploy-meetings-microsoft-teams-landing-page.md)

2.  Informe a los usuarios sobre los Teams. Descargue el kit de éxito de [Teams para Clientes](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) obtenga presentaciones, correos electrónicos de ejemplo, pósteres y guías de introducción.


5.  Asegúrese de que sus empleados tengan acceso a Internet y ancho de banda apropiados para Teams Use las instrucciones de [ Prepare la red de su organización para los Teams](prepare-network.md) para obtener más información sobre cómo hacerlo.
    - El ancho de banda limitado puede afectar a la calidad de audio en las reuniones de Teams. Para garantizar una mejor experiencia de reunión en condiciones de poco ancho de banda, Anime a los usuarios a limitar el vídeo y usar PSTN para las llamadas y el audio de la reunión. 

    - Si necesita ayuda para solucionar problemas o solucionarlos con la calidad de la llamada o la reunión, siga las instrucciones de [problema conocido: marcado en Skype Empresarial y los ID. de conferencia](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) en la parte inferior de este artículo.

2.  [Envíe vínculos de formación](enduser-training.md) para ayudar a los empleados a sacar el máximo rendimiento de Teams
    
3. Lea nuestro nuevo contenido sobre el trabajo remoto y cómo compartirlo con los usuarios:
        
      - Blog de los Teams (28 de febrero de 2020): [4 sugerencias para trabajar desde casa con Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Colaborar con Office 365](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Trabajar de forma remota con Teams y Office 365](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  Anime a todos los usuarios a [instalar](get-clients.md#mobile-clients) y usar la aplicación móvil:[IOS](https://go.microsoft.com/fwlink/?LinkId=835758)  [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > Si está en China, visite aquí [obtener equipos para Android en China.](get-teams-android-in-china.md)

4.  Doten de personal al[servicio de asistencia](troubleshoot-installation.md) para tratar las consultas de los usuarios


## <a name="communications"></a>Comunicaciones

Use los Teams para mantenerse en contacto con sus empleados:
- [Equipos de la organización](create-an-org-wide-team.md) y [la plantilla de la aplicación Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator)
    
- Envíe información acerca de las directivas de trabajo desde casa, salud y seguridad de su organización
    
- Use [Eventos en directo](teams-live-events/what-are-teams-live-events.md) para reuniones y la divulgación en toda la empresa Para las reuniones de más de 250 participantes, haga que se convierta en un evento en directo. 

## <a name="personal-considerations"></a>Consideraciones personales

Aquí se muestran algunas sugerencias para trabajar desde casa correctamente:

- Cuente con un espacio de trabajo físico definido con un buen alumbrado y una ergonomía adecuada.

- Establezca límites claros en sus horas de trabajo y compromisos, y use el [estado de presencia](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) de los Teams para indicar cuando esté ausente.

- "Viaje" hacia y desde su oficina de trabajo desde casa voluntariamente; no convierta el trabajo desde casa en trabajo a domicilio.

- Levántese y tómese un descanso periódicamente. Vaya a dar un paseo, haga estiramientos, prepárese una taza de té.

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>Problema conocido: Marcando en Skype para identificaciones de conferencias de Empresas o Teams

El siguiente es un resumen del 7 de febrero de 2020 post al centro de mensajes (MC203397):

Microsoft sabe que algunos usuarios de la región de China tienen problemas para llamar a las identificaciones de las conferencias de Skype para Empresas o Teams. Estos problemas son, en la mayoría de los casos, externos a los sistemas bajo nuestro control. Por lo general, el problema es con las compañías locales de telefonía móvil y de telecomunicaciones. 

Si tiene problemas con las conferencias de audio, le recomendamos lo siguiente:

- Pregunte al autor de llamada o al organizador de la reunión para llamar a un número de teléfono móvil o RTC
- Unirse a la llamada o reunión desde los clientes de escritorio o móviles con VoIP

Si necesita registrar una solicitud de soporte técnico, debe incluir lo siguiente:
    
- Hora exacta de la llamada
- Número de puente de conferencia marcado
- La red telefónica de llamadas
- Número de teléfono del autor de la llamada
