---
title: Planeación del conector de datos de llamadas | Análisis híbrido de supervisión del panel de calidad de llamadas
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general sobre el uso de herramientas de telemetría de Skype Empresarial Online para supervisar una implementación local en un escenario híbrido.
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221320"
---
# <a name="plan-call-data-connector"></a>Plan del conector de datos de llamada

## <a name="overview"></a>Información general

En este tema se describen las ventajas, las consideraciones de planeación y los requisitos para implementar el conector de datos de llamadas de Skype Empresarial Server. Para obtener más información sobre cómo configurar el conector de datos de llamadas, vea [Configurar el conector de datos de llamadas.](configure-call-data-connector.md)


Call Data Connector simplifica en gran medida la supervisión de llamadas en un entorno híbrido porque ya no necesita usar diferentes conjuntos de herramientas locales y en línea para supervisar la calidad de las llamadas de todos los usuarios. Independientemente de si los usuarios están ubicados localmente o en línea, puede elegir ver la calidad de las llamadas para toda la organización en línea.

Con Call Data Connector, puede realizar las siguientes tareas mediante un único conjunto de herramientas:

- Supervise su experiencia de usuario en Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server.

- Ver y solucionar problemas en la red.

- Asigne roles de administrador y departamento de soporte técnico para El análisis de llamadas, de modo que pueda ayudar a los trabajadores del departamento de soporte técnico a ver y solucionar los problemas de sus áreas de responsabilidad.

Con el conector de datos de llamadas, Skype Empresarial Server inserta datos de llamadas en el servicio en la nube para que pueda aprovechar las herramientas análisis de llamadas (CA) y panel de calidad de llamadas (CQD) de Skype Empresarial Online, como se muestra en el siguiente diagrama:

![Correo de voz en la nube de SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

El servidor inserta los datos de calidad de la experiencia (QoE) y registro detallado de llamadas (CDR) en el servicio en línea.

Las herramientas de análisis de llamadas y CQD le permiten supervisar la calidad de las llamadas y solucionar problemas de conexión con Microsoft Teams y los servicios de Skype Empresarial de la siguiente manera:

- Análisis de llamadas se centra en problemas de calidad con llamadas específicas. Muestra información detallada sobre las llamadas y reuniones de cada usuario en una cuenta de Skype Empresarial.  Con Análisis de llamadas, puede asignar permisos a un operador del departamento de soporte técnico que, a continuación, puede supervisar las llamadas sin tener acceso al resto del Centro de administración de Skype Empresarial.

- El Panel de calidad de llamadas se centra en el rendimiento de la red y en los problemas de toda la organización. Los administradores e ingenieros de red de Skype Empresarial usan esta herramienta para solucionar problemas y optimizar el rendimiento de la red.

Para obtener más información, consulte [Análisis de llamadas y Panel de calidad de llamadas.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Por supuesto, es posible que desee mantener algunos datos de calidad de llamadas localmente. Este podría ser el caso, por ejemplo, si usa una solución de terceros con informes y flujos de trabajo personalizados.  El conector de datos de llamadas le permite configurar el envío de datos al servicio en línea a la vez que mantiene una copia de los datos en el servidor local, como se muestra en el siguiente diagrama:

![Correo de voz en la nube de SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requirements

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server implementado en una topología compatible.  Para obtener más información acerca de la implementación de Skype Empresarial Server y las [topologías admitidas,](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)consulte Conceptos básicos de la topología. Para configurar el conector de datos de llamadas, debe:

- Habilite la conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar el conector de datos de llamadas, debe asegurarse de que tiene configurada la conectividad híbrida entre los entornos locales y en línea. A veces, esto se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Autentique su organización de Microsoft 365 u Office 365 y asegúrese de que tiene los siguientes roles habilitados:

  - Administrador de Skype Empresarial Server
  - Administrador global de Microsoft 365 u Office 365

- Si aún no lo ha hecho, active el Panel de calidad de llamadas como se describe en Activar y usar el Panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Habilite el grupo de servidores front-end para supervisión, con bases de datos locales LCSCdr y QoEMetrics. Sin esto, el conector de datos de llamadas no tendrá datos de métricas con los que trabajar.

> [!IMPORTANT]
> El conector de datos de llamadas no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

- Autenticación de servidor a servidor configurada [correctamente.](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparación de informes del Panel de calidad de llamadas (CQD) local y en línea

| Informes de características | Skype Empresarial Online | Skype Empresarial Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de uso compartido de aplicaciones |Sí | Limitado |
| Información de creación de clientes| Sí | Sí |
| Análisis de exploración en profundidad | Sí | No |
| Métricas de confiabilidad de medios | Sí | Limitado |
| Informes de configuración | Sí | Sí |
| Informes de información general | Sí | No |
| Informes por usuario | Sí | Sí |
| Personalización del conjunto de informes <br> (agregar, eliminar, modificar informes) | Sí | Sí |
| Métricas de uso compartido de pantalla basado en vídeo | Sí | No |
| API de datos para el acceso mediante programación <br> a CQD | No | Sí |
||||
