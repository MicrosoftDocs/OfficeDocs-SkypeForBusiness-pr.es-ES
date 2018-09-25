---
title: Análisis de llamada y el panel de calidad de llamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
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
ms.openlocfilehash: 8d41e051a7f55c24c3388e707648970bb1ab64df
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013550"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Análisis de llamada y el panel de calidad de llamada

Microsoft Teams y Skype para la empresa le ofrecen dos maneras para supervisar y solucionar los problemas de calidad de la llamada: análisis de llamadas y panel de calidad de llamadas. En este artículo se describe ambos y se indica cuándo se debe usar cada uno de ellos.
  
**Análisis de llamada está ahora disponible en el Microsoft Teams y Skype para el centro de administración de negocio.** Para ver toda la información de la llamada y los datos para un usuario, utilice la ficha **Historial de llamadas** . Para ello, puede buscar en la página de perfil del usuario buscando el usuario desde el panel o buscar el usuario de **los usuarios** en el panel de navegación izquierdo.

> [!IMPORTANT]
> Permisos de agente de departamento de soporte técnico y la carga de la topología de red estará disponibles en el nuevo portal de administración en los próximos meses. Mientras tanto, puede seguir usando https://adminportal.services.skypeforbusiness.com para el acceso de departamento de soporte técnico de nivel 1 y nivel 2.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>¿Qué es el análisis de llamadas, y cuándo debo usarlo?

Análisis de la llamada muestran información detallada acerca de los dispositivos, redes y conectividad relacionadas con las llamadas específicas y las reuniones para cada usuario en un Microsoft Teams o Skype para la cuenta de empresa. Si usted es un administrador de Office 365, puede usar llamar análisis para solucionar problemas de conexión y la calidad de llamada en Microsoft Teams y Skype para la empresa.

Para ver esta información para un usuario en el Microsoft Teams y Skype para el centro de administración de negocio, haga clic en la ficha **Historial de llamadas** para ese usuario en la página de detalles del usuario, que muestra todas las llamadas y las reuniones que el usuario ha participado en para los últimos 30 días.

![Llame al análisis de datos de usuario.](media/call-analytics-user-data.png)

Para obtener información adicional acerca de una sesión determinada, incluidos los medios detalladas y las estadísticas de red, haga clic en una sesión para ver los detalles.

![Llame al análisis de datos de sesión de usuario.](media/call-analytics-user-data-session.png)

Si desea que no son de administrador, como agentes de departamento de soporte técnico de un proveedor externo, para usar el análisis de llamadas, puede asignar permisos para que pueden utilizar llamadas análisis pero no pueden obtener acceso el resto de la Skype para el centro de administración empresarial: 
  
- **Los agentes del departamento de soporte técnico con permisos de nivel 1**: agentes vea un conjunto limitado de datos y la información de identificación personal (PII) en análisis de llamadas. Pueden solucionar problemas de las llamadas, pero problemas con las reuniones se entregan a un agente de nivel 2.
    
- **Los agentes del departamento de soporte técnico con permisos de nivel 2**: los agentes vea todos los datos disponibles en análisis de llamadas y solucionar problemas de llamadas y las reuniones. Tienen acceso completo para llamar a los registros y la información del cliente.

> [!IMPORTANT]
> Permisos de agente de departamento de soporte técnico y la carga de la topología de red estará disponibles en el nuevo portal de administración en los próximos meses. Mientras tanto, puede seguir usando https://adminportal.services.skypeforbusiness.com para el acceso de departamento de soporte técnico de nivel 1 y nivel 2.
    
Para obtener información detallada sobre la configuración de análisis de llamadas, vea [Set up Skype para llamadas de Business Analytics](set-up-call-analytics.md). Para obtener más información acerca de cómo los agentes del departamento de soporte técnico puede trabajar con análisis de llamadas, vea [Uso de llamadas de análisis para solucionar problemas de calidad de la llamada deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>¿Qué es el panel de calidad de llamadas y cuándo debo usarlo?

Análisis de llamada le ofrece información específica detallada acerca de la calidad de llamada tuvo por los usuarios. ¿Por qué tenía una llamada deficiente esta tarde usuario Tony Smith? Uso de análisis de llamadas, puede investigar un Microsoft Teams o Skype para administración empresarial o agente del departamento de soporte técnico capacitados del dispositivo, red, conectividad y otros factores relacionados con la llamada de Tomás.
  
Donde entidad de certificación está diseñada para ayudar a los administradores y los agentes del departamento de soporte técnico solución los problemas de calidad de llamada con llamadas específicas, el panel de calidad de llamadas (CQD) está diseñado para ayudar a Skype para los administradores de negocio e ingenieros de red optimizan una red. CQD lleva el enfoque de usuarios específicos y en su lugar, busca información de agregado para un Skype todo para la organización empresarial. 
  
Quizá la calidad de llamadas deficientes de Tomás es debido a un problema de red que también está afectando a muchos otros usuarios. Experiencia de llamada individual de Tomás no está visible en CQD, pero se captura la calidad general de las llamadas realizadas mediante Skype para la empresa. Con el CQD general patrones pueden ponerse de manifiesto, que los ingenieros de red realizar las evaluaciones informadas de calidad de la llamada. CQD proporciona informes de métricas de calidad de llamada que le brindarán en general llamada calidad, servidor cliente y secuencias de cliente a cliente y calidad de voz [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Captura de pantalla del panel de calidad de llamada en el Skype para el centro de administración de negocio. Las fichas que se muestran son calidad de llamada general, servidor - cliente, cliente - cliente y SLA de calidad de la vista.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obtener más información, vea [características del panel de calidad de llamada de Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Análisis de la llamada y CQD ejecutarán en paralelo y pueden usarse independientemente o juntos. Por ejemplo, supongamos que un agente de nivel 1 determina que necesitan más ayuda para solucionar un problema de la llamada. El agente de nivel 1, pasa la llamada a un agente de nivel 2, que tiene acceso para obtener más información de análisis de llamadas que el agente de nivel 1. A su vez, el agente de nivel 2 puede alertar a un ingeniero de red a un problema. El ingeniero de red puede comprobar CQD para ver si un problema relacionado con el sitio global podría ser un colaborador causa de los problemas de la llamada.
  
Para obtener más información sobre CQD, vea [activar y con el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md) y [las dimensiones y medidas disponibles en el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea de](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el análisis de llamadas](set-up-call-analytics.md)

[Usar Análisis de llamadas para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)