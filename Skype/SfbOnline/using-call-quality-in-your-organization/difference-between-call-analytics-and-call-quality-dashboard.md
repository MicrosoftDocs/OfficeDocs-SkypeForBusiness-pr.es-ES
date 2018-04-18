---
title: ¿Cuál es la diferencia entre llamar a Analytics y llamar al panel de calidad?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Obtenga información acerca de Analytics llamar y llamar al panel de calidad y cuándo utilizarlos para supervisar y solucionar problemas de calidad de la llamada en Skype para el negocio.
ms.openlocfilehash: 869b4373d6e1bea65700532b52959aa2126d94d9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a>¿Cuál es la diferencia entre llamar a Analytics y llamar al panel de calidad?

Skype para empresas le ofrece dos maneras de supervisar y solucionar los problemas de calidad de llamadas: llamar a Analytics y llamar al panel de calidad. Este artículo describe ambos e indica cuándo utilizar cada uno de ellos.
  
> [!NOTE]
> Análisis de llamada está en vista previa. Texto e imágenes que se describe aquí pueden no coincidir con su experiencia. 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>¿Qué es llamar a Analytics y cuándo debo usarlo?

Llamada Analytics muestra información detallada acerca de los dispositivos, redes y conectividad de las llamadas concretas y reuniones para cada usuario de un Skype para la cuenta de empresa. Si eres un Skype para la administración de negocios, puede utilizar Analytics llamar para solucionar problemas de calidad y conexión de llamada de negocio Skype.
  
Si desea que no son de administrador, como agentes de asistencia técnica de un proveedor externo, para utilizar Analytics llamar, puede asignar permisos para que pueden utilizar Analytics llamar pero no puede acceder al resto de la Skype para el centro de administración de negocio: 
  
- **Los agentes de asistencia técnica con permisos de nivel 1**: agentes consulte un conjunto limitado de datos e información personal identificable (PII) en llamar a Analytics. Puede solucionar los llamadas, pero los problemas con las reuniones se entregan a un agente de nivel 2.
    
- **Los agentes de asistencia técnica con permisos de nivel 2**: agentes vea todos los datos disponibles en llamar a Analytics y solucionar problemas de llamadas y reuniones. Tienen acceso completo para llamar a los registros y la información del cliente.
    
Para obtener más información acerca de cómo configurar Analytics llamar, consulte [Configurar Skype para llamar de Business Analytics](set-up-call-analytics.md). Para obtener más información sobre cómo pueden trabajar los agentes de asistencia técnica con Analytics llamar, consulte [Uso llamar análisis para solucionar problemas de calidad de sonido deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>¿Qué es el panel de calidad llamar y cuándo debo usarlo?

Llamada Analytics proporciona información detallada y específica sobre la calidad de las llamadas experimentada por los usuarios. ¿Por qué usuario Tony Smith tuvo una mala llamada esta tarde? Con llamar a Analytics, puede investigar un Skype negocio admin o el agente de asistencia capacitado del dispositivo, red, conectividad y otros factores relacionados con la llamada de Tony.
  
Donde CA está diseñado para ayudar a los administradores y los agentes de asistencia técnica llamada calidad solucionar problemas relacionados con llamadas concretas, el tablero de mandos de calidad llamar (CQD) está diseñado para ayudar a Skype para los administradores de negocios y los ingenieros de red optimizan una red. CQD cambia el foco de usuarios específicos y en su lugar busca información de agregado para un Skype todo para la organización empresarial. 
  
Tal vez la calidad de sonido deficiente de Tony es debido a un problema de red que también afecta a otros muchos usuarios. Experiencia de llamadas individual de Tony no está visible en el CQD, pero se captura la calidad de las llamadas realizadas con Skype para el negocio. Con el CQD general patrones pueden ponerse de manifiesto, que los ingenieros de red puedan efectuar evaluaciones informadas de la calidad de las llamadas. CQD proporciona informes de métricas de calidad de llamada que le brindarán en general llamar a calidad, servidor cliente y secuencias de cliente a cliente y [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de calidad de voz. 
  
![Captura de pantalla de panel de calidad de la llamada en el Skype para el centro de administración de negocios. Fichas que se muestran son calidad general llamar, servidor - cliente, cliente - cliente y SLA de calidad de la vista.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obtener más información, vea [características del panel de calidad llamar de Skype para los negocios en línea](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Análisis de llamada y CQD ejecutan en paralelo y se pueden usar independientemente o juntos. Por ejemplo, que un agente de nivel 1 determina que necesitan más ayuda para solucionar un problema de la llamada. El agente de nivel 1 pasa la llamada a un agente de nivel 2, que tiene acceso a más información en Analytics llamar a que el agente de nivel 1. A su vez, el agente de nivel 2 puede alertar a un ingeniero de red para un problema. El ingeniero de red puede consultar CQD para ver si un problema relacionado con el sitio global podría ser una contribuyente causa de los problemas de la llamada.
  
Para obtener más información sobre CQD, consulte [activar y con llamar al panel de calidad para los equipos de Microsoft y Skype para los negocios en línea](turning-on-and-using-call-quality-dashboard.md) y [dimensiones y medidas disponibles en llamar al panel de calidad para los equipos de Microsoft y Skype para los negocios en línea](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>See also
[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el análisis de llamadas para solucionar problemas de mala calidad de llamada en Skype Empresarial](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 