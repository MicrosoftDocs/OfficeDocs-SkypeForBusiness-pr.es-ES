---
title: Análisis de llamadas y Panel de calidad de llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Obtenga información sobre el análisis de llamadas y, a continuación, llame al panel de calidad y cuándo usarlos para supervisar y solucionar los problemas de calidad de la llamada.
ms.openlocfilehash: e8c9331a26caf5e2fe4cb618ac896393d35939ba
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460855"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Análisis de llamadas y Panel de calidad de llamadas

Microsoft Teams y Skype para la empresa le ofrecen dos maneras para supervisar y solucionar los problemas de calidad de la llamada: análisis de llamadas y panel de calidad de llamadas. En este artículo se describe ambos y se indica cuándo se debe usar cada uno de ellos.

Análisis de la llamada y CQD ejecutarán en paralelo y pueden usarse independientemente o juntos. Por ejemplo, una especialista en soporte técnico determina que necesitan más ayuda para solucionar un problema de llamada de las comunicaciones. El especialista en soporte técnico de comunicaciones pasa la llamada a un ingeniero de soporte de comunicaciones, quién tiene acceso a más información en análisis de llamadas de la especialista en soporte de las comunicaciones. A su vez, el ingeniero de soporte de comunicaciones puede alertar a un ingeniero de red a un problema. El ingeniero de red podría comprobar CQD para ver si un problema relacionado con el sitio global podría ser un colaborador causa de los problemas de la llamada.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>¿Qué es el análisis de llamadas, y cuándo debo usarlo?

**Análisis de la llamada está ahora disponible en el [Centro de administración de equipos de Microsoft](https://admin.teams.microsoft.com).** Para ver toda la información de la llamada y los datos para un usuario, utilice la ficha **Historial de llamadas** . Para ello, puede buscar en la página de perfil del usuario buscando el usuario desde el panel o buscar el usuario de **los usuarios** en el panel de navegación izquierdo.

Análisis de la llamada muestran información detallada acerca de los dispositivos, redes y conectividad relacionadas con las llamadas específicas y las reuniones para cada usuario en un Microsoft Teams o Skype para la cuenta de empresa. ¿Por qué este usuario tiene una llamada deficiente esta tarde? Uso de análisis de llamadas, un agente de departamento de soporte técnico capacitados o administración de Office 365 puede investigar el dispositivo, red, conectividad y otros factores relacionados con su llamada a solucionar problemas de conexión y la calidad de llamada en Microsoft Teams y Skype para la empresa.

Para ver esta información para un usuario en el centro de administración de Microsoft Teams, haga clic en la ficha **Historial de llamadas** para ese usuario en la página de detalles del usuario, que muestra todas las llamadas y las reuniones que el usuario ha participado en para los últimos 30 días.

![Llame al análisis de datos de usuario.](media/call-analytics-user-data.png)

Para obtener información adicional acerca de una sesión determinada, incluidos los medios detalladas y las estadísticas de red, haga clic en una sesión para ver los detalles.

![Llame al análisis de datos de sesión de usuario.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Si desea que no son de administrador, como agentes de departamento de soporte técnico de un proveedor externo, para usar el análisis de llamadas, puede asignar permisos para que pueden utilizar análisis de llamada, pero no pueden obtener acceso el resto del centro de administración de Microsoft Teams: 
  
- **Los agentes del departamento de soporte técnico con las comunicaciones admiten permisos especialista**: agentes vea un conjunto limitado de datos y la información de identificación personal (PII) en análisis de llamadas. Pueden solucionar problemas de las llamadas, pero problemas con las reuniones se entregan a un ingeniero de soporte técnico de comunicaciones.
    
- **Los agentes del departamento de soporte técnico con las comunicaciones admiten permisos de ingeniería**: los agentes vea todos los datos disponibles en análisis de llamadas y solucionar problemas de llamadas y las reuniones. Tienen acceso completo para llamar a los registros y la información del cliente.

> [!NOTE]
> La función de especialista en soporte técnico de communications es equivalente a la función de soporte técnico de nivel 1 desde el portal de vista previa y la función de ingeniero de soporte técnico de comunicaciones es equivalente a la función de soporte técnico de nivel 2 desde el portal de vista previa.

Para obtener más información acerca de las comunicaciones especialista en soporte técnico y comunicaciones admite ingeniero de roles, consulte [roles de administrador de equipos de uso de Microsoft para administrar los equipos](using-admin-roles.md).

> [!IMPORTANT]
> Permisos de agente de departamento de soporte técnico y la carga de la topología de red están disponibles en el centro de administración de Microsoft Teams. Especialistas en soporte técnico de comunicaciones y los ingenieros de soporte técnico de comunicaciones pueden usar este portal para obtener acceso a análisis de llamadas y el panel de calidad de llamadas.
    
Para obtener información detallada sobre la configuración de análisis de llamadas, vea [Set up Skype para llamadas de Business Analytics](set-up-call-analytics.md). Para obtener más información acerca de cómo los agentes del departamento de soporte técnico puede trabajar con análisis de llamadas, vea [Uso de llamadas de análisis para solucionar problemas de calidad de la llamada deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>¿Qué es el panel de calidad de llamadas y cuándo debo usarlo?
  
Donde entidad de certificación está diseñada para ayudar a los administradores y los agentes del departamento de soporte técnico solución los problemas de calidad de llamada con llamadas específicas, el panel de calidad de llamadas (CQD) está diseñado para ayudar a los administradores de Microsoft Teams, Skype para los administradores de negocios, y los ingenieros de red optimizan una red. CQD lleva el enfoque de usuarios específicos y en su lugar busca en la información de agregado de toda una Microsoft Teams o Skype organización empresarial. Para obtener más información, vea [características del panel de calidad de llamada de Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Quizá la calidad de llamadas deficientes del usuario es debido a un problema de red que también está afectando a muchos otros usuarios. La experiencia de llamada individuales no está visible en CQD, pero se captura la calidad general de las llamadas realizadas mediante Microsoft Teams o Skype para la empresa. Con el CQD general patrones pueden ponerse de manifiesto, que los ingenieros de red realizar las evaluaciones informadas de calidad de la llamada. CQD proporciona informes de métricas de calidad de llamada que le brindarán en general llamada calidad, secuencias de cliente a servidor, secuencias de cliente a cliente y calidad de voz [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Captura de pantalla del panel de calidad de llamada. Las fichas que se muestran son calidad de llamada general, servidor - cliente, cliente - cliente y SLA de calidad de voz.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Con la Ayuda de informes de Location-Enhanced del CQD, se pueden evaluar la calidad de llamada agregado y la confiabilidad dentro de creación del usuario para determinar si el problema se aísla a un solo usuario o afecta a un segmento mayor de usuarios.

![Captura de pantalla de informes de mejorado a la ubicación del panel de calidad de llamada. Las fichas que se muestran son información general, los edificios - cableada, los edificios - WiFi y Mobile (LTE). Se aplica un filtro para ver las secuencias dentro de un edificio específico.](media/call-quality-dashboard-location-enhanced-reports-building-selection.png)

> [!NOTE]
> Para habilitar las vistas específicas de creación en CQD, un administrador debe [cargar información de creación](turning-on-and-using-call-quality-dashboard.md#BKMKBuildingInformationUpload) de página del CQD inquilino la carga de datos.

Si desea que no son de administrador, como agentes de departamento de soporte técnico, para usar el panel de calidad de llamadas, puede asignar a los usuarios la función de **Ingeniero de soporte técnico de los equipos de comunicaciones**, **Especialista en soporte técnico de comunicaciones de los equipos**o **Lector de informes** . Los usuarios con las siguientes funciones de pueden tener acceso a los paneles de calidad de llamadas:

- Administrador global
- Skype para el Administrador de negocio
- Administrador de servicios de Teams
- Administrador de comunicaciones de Teams
- Ingeniero de soporte en comunicaciones de Teams
- Especialista en soporte técnico de comunicaciones de los equipos
- Lector de informes

> [!NOTE]
> Las funciones de ingeniero de soporte técnico de los equipos de comunicaciones, especialista en soporte técnico de los equipos de comunicaciones y lector de informes no pueden modificar los archivos en la página de carga de datos de inquilinos del CQD ni activar CQD para un inquilino.

Para obtener más información acerca de estas funciones, vea [roles de administrador acerca de Office 365](/office365/admin/add-users/about-admin-roles).

Para obtener más información sobre CQD, vea [activar y con el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md) y [las dimensiones y medidas disponibles en el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea de](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Temas relacionados

[Vídeo: Información general de la calidad de llamada](https://aka.ms/teams-quality)

[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activar y con el panel de calidad de llamadas para Microsoft Teams y Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md)
