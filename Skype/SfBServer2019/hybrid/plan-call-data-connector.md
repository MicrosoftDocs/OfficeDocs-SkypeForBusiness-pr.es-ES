---
title: Planeación de conector de datos de llamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general del uso de Skype para herramientas de telemetría de negocio en línea para supervisar una implementación local en un escenario híbrido.
ms.openlocfilehash: e9039d3865e3baf5740f4f7489b1a7cfec6dea98
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696215"
---
# <a name="plan-call-data-connector"></a>Planeación de conector de datos de llamada

## <a name="overview"></a>Información general
Este tema describe las ventajas, las consideraciones de planeación y requisitos para la implementación de Skype para el conector de datos de llamadas de Business Server. Para obtener más información acerca de cómo configurar el conector de datos de llamadas, vea [Configuración de conector de datos de llamada](configure-call-data-connector.md).

> [!NOTE]
> En la versión preliminar pública, panel de análisis de llamadas sólo está disponible.

Conector de datos de llamada simplifica en gran medida la llamada de supervisión en un entorno híbrido debido a que ya no necesita usar distintos conjuntos de herramientas en línea y local para supervisar todos los de la calidad de las llamadas a los usuarios. Si los usuarios están hospedados en local o en línea, puede elegir ver la calidad de las llamadas para toda la organización en línea.

Con el conector de datos de llamadas, puede realizar las siguientes tareas mediante el uso de un único conjunto de herramientas:

- Supervisar la experiencia del usuario a través de Microsoft Teams, Skype para profesionales en línea y Skype para Business Server.

- Ver y solucionar los problemas a través de la red.

- Asignación de roles de departamento de soporte técnico y administrador para análisis de llamadas, por lo que puede ofrecer a los trabajadores del departamento de soporte técnico ver y solucionar problemas de sus áreas de responsabilidad. 

Con el conector de datos de llamadas, la Skype para Business Server inserta datos de la llamada al servicio de nube para que puede aprovechar la Skype para herramientas de análisis de llamadas en línea en Business (CA) y el panel de calidad de llamadas (CQD), tal como se muestra en el siguiente diagrama:

![Correo de voz de SfB en la nube](../../sfbserver2019/media/call-data-connector-plan-1.png)

El servidor inserta la calidad de la experiencia (QoE) y datos de registro de detalles de llamadas (CDR) para el servicio en línea.

Las herramientas CQD y análisis de llamadas permiten supervisar la calidad de las llamadas y solucionar problemas de conexión con Microsoft Teams y Skype para servicios de negocios de la siguiente manera:

- Llamar a enfoques de análisis acerca de problemas de calidad de llamadas específicas. Muestra información detallada sobre las reuniones para cada usuario y las llamadas en un Skype para la cuenta de empresa.  Con el análisis de llamadas, puede asignar permisos a un operador de departamento de soporte técnico que, a continuación, se puede supervisar las llamadas sin tener acceso al resto de la Skype para el centro de administración de negocio.

- Panel de calidad de llamada se centra en el rendimiento de la red y problemas en toda la organización. Skype para los administradores de negocios e ingenieros de red use esta herramienta para solucionar problemas y optimizar el rendimiento de la red.

Para obtener más información, vea [análisis de llamadas y panel de calidad de llamadas](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Por supuesto, es posible que desee mantener algunos datos de calidad de llamada local. Esto puede suceder, por ejemplo, si está utilizando una solución de terceros con los flujos de trabajo e informes personalizados.  Conector de datos de llamada permite configurar el envío de datos para el servicio en línea mientras se mantiene también una copia de los datos en el servidor local, tal como se muestra en el siguiente diagrama:

![Correo de voz de SfB en la nube](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a>Requisitos

Los siguientes requisitos se suponen que ya dispone de Skype para Business Server implementado en una topología admitida.  Para obtener más información sobre la implementación de Skype para Business Server y las topologías admitidas, vea [Conceptos básicos de la topología](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Para configurar el conector de datos de llamadas, debe:

- Habilitar la conectividad híbrida. Si ya dispone de Skype para Business Server implementado y que desea habilitar el conector de datos de llamadas, debe asegurarse de que dispone de conectividad híbrida configurar entre los entornos en línea y local. En ocasiones, esto se denomina una configuración de dominio dividido. 

   Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Office 365](plan-hybrid-connectivity.md) y [Configure la conectividad híbrida entre Skype para Business Server y Office 365](configure-hybrid-connectivity.md).

-  Autenticar a su inquilino Office 365 y asegúrese de que tiene las siguientes funciones habilitadas:

   - Skype para el administrador del servidor de negocio 
   - Administrador Global de Office 365 

- Si no lo ha hecho ya, activar en el panel de calidad de llamada tal como se describe en [activar y con el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea](/microsoftteams/turning-on-and-using-call-quality-dashboard).
 
- Habilitar el grupo de servidores front-end de supervisión, con bases de datos LCSCdr y QoEMetrics locales. Sin esto, llame al conector de datos no tiene datos de métricas para que funcione con. 
 
> [!IMPORTANT]
> Conector de datos de llamada no funcionará si no está habilitada la supervisión en el grupo de servidores front-end.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Informes de comparación de local y panel de calidad de llamadas en línea (CQD)

| Informes de característica | Skype Empresarial Online | Skype Empresarial Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de uso compartido de aplicaciones |Sí | Limitado |
| Información de creación de cliente| Sí | Sí |
| Análisis en profundidad | Sí | No |
| Métricas de confiabilidad de medios | Sí | Limitado |
| Informes de fábrica | Sí | Sí |
| Información general sobre informes | Sí | No |
| Por informes de usuario | Sí | Sí |
| Personalización del conjunto de informes <br> (agregar, eliminar, modificar informes) | Sí | Sí |
| Uso compartido de las métricas de pantalla basados en vídeo | Sí | No |
| API de datos para el acceso mediante programación <br> a CQD | No | Sí |
||||
