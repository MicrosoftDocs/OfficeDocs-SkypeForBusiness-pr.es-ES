---
title: "¿Cuál es la diferencia entre el análisis de llamadas y panel de calidad de llamada?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# ¿Cuál es la diferencia entre el análisis de llamadas y panel de calidad de llamada?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Skype Empresarial le ofrece dos formas para supervisar y solucionar problemas de calidad de la llamada: análisis de llamadas y panel de calidad de llamadas. En este artículo se describe ambos y se indica cuándo usar cada uno de ellos.
  
> [!NOTE]
> Análisis de llamada está en vista previa. Texto e imágenes que se describen aquí no pueden coincidir con su experiencia. 
  
## ¿Qué es el análisis de llamadas y cuándo debo usarlo?

Análisis de llamada muestra información detallada sobre la conectividad relacionados con las reuniones para cada usuario de una cuenta de Skype Empresarial o llamadas específicas, redes y dispositivos. Si es un administrador de Skype Empresarial, puede usar el análisis de llamada para solucionar problemas de conexión y la calidad de llamada Skype Empresarial.
  
Si desea que no sean administradores, como agentes de departamento de soporte técnico de un proveedor externo, para usar el análisis de llamadas, puede asignar permisos para que pueden usar el análisis de llamada, pero no puede acceder al resto del centro de administración de Skype Empresarial:
  
- **Departamento de soporte técnico agentes con permisos de nivel 1**: agentes vea un conjunto de datos y la información de identificación personal (PII) en llamar análisis limitado. Pueden solucionar problemas de llamadas, pero los problemas con las reuniones se entregan con un agente de nivel 2.
    
- **Departamento de soporte técnico agentes con permisos de nivel 2**: agentes ver todos los datos disponibles en el análisis de llamadas y solucionar problemas de llamadas y reuniones. Tienen acceso completo a la información del cliente y registros de llamadas.
    
Para obtener más información sobre cómo configurar el análisis de llamadas, consulte [Configurar Skype para Business Analytics de llamadas](set-up-skype-for-business-call-analytics.md). Para obtener más información acerca de cómo agentes del departamento de soporte técnico pueden trabajar con el análisis de llamadas, consulte [Calidad de llamadas de análisis de uso llamar a solucionar problemas de una mala Skype para la empresa](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md).
  
## ¿Qué es el panel de calidad de llamadas y cuándo debo usarlo?

Análisis de llamada proporciona información específica detallada acerca de la calidad de llamada experimentada por los usuarios. ¿Por qué tenía usuario Tony Smith a una llamada de una mala esta tarde? Mediante el análisis de llamadas, un administrador de Skype Empresarial o el agente de servicio de asistencia capacitado puede investigar el dispositivo, red, conectividad y otros factores relacionados con la llamada de Diego.
  
Donde está diseñado para ayudar a los administradores y agentes del departamento de soporte técnico solución problemas de calidad de llamada con llamadas específicas, el panel de calidad de llamadas (CQD) está diseñado para ayudar a los administradores de Skype Empresarial e ingenieros de red optimizan una red. CQD desplaza el enfoque de usuarios específicos y busca en su lugar agregado información para una organización completa Skype Empresarial.
  
¿La calidad de llamada deficiente de Diego es debido a un problema de red que también afecta a muchos otros usuarios. Experiencia de llamada individuales de Diego no está visible en CQD, pero se genera la calidad general de las llamadas realizadas mediante Skype Empresarial. Total con la CQD tramas pueden ser evidentes, que los ingenieros de red realizar evaluaciones informadas de calidad de la llamada. CQD proporciona informes de métrica de calidad de llamada que proporcionan recomendaciones sobre general llamar calidad, secuencias de cliente de servidor y cliente de cliente y calidad de voz [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Para obtener más detalles, vea [Características del panel de calidad de llamadas de Skype Empresarial Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD).
  
Análisis de llamada y CQD ejecutarán en paralelo y pueden usar independientemente o juntos. Por ejemplo, que un agente de nivel 1 determina que necesitan más ayuda para solucionar un problema de llamada. El agente de nivel 1 pasa la llamada a un agente de nivel 2, quién tiene acceso a más información en el análisis de llamar a que el agente de nivel 1. A su vez, el agente de nivel 2 puede alertar a un técnico de red para un problema. Ingeniería de red puede comprobar CQD para ver si los problemas generales relacionados con el sitio podrían ser un colaborador causa de problemas de la llamada.
  
Para obtener más información sobre CQD, consulte [Activar y usar el panel de calidad de llamada para Teams de Microsoft y Skype empresarial Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md) y[Dimensiones y medidas disponibles en panel de calidad de llamada para Teams de Microsoft y Skype empresarial Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

