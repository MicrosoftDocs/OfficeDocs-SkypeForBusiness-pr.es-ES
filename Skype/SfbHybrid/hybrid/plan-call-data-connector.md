---
title: Plan Call Data Connector | Análisis híbrido de supervisión de panel de calidad de llamadas
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
description: Introducción al uso de herramientas de telemetría de Skype Empresarial Online para supervisar una implementación local en un escenario híbrido.
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110556"
---
# <a name="plan-call-data-connector"></a>Plan del conector de datos de llamada

## <a name="overview"></a>Información general

En este tema se describen las ventajas, consideraciones de planeación y requisitos para implementar Skype Empresarial Server Call Data Connector. Para obtener más información sobre la configuración de Call Data Connector, vea [Configure Call Data Connector](configure-call-data-connector.md).


Call Data Connector simplifica en gran medida la supervisión de llamadas en un entorno híbrido porque ya no es necesario usar diferentes conjuntos de herramientas locales y en línea para supervisar la calidad de llamadas de todos los usuarios. Independientemente de si los usuarios están ubicados localmente o en línea, puede elegir ver la calidad de las llamadas para toda la organización en línea.

Con Call Data Connector, puede realizar las siguientes tareas mediante un único conjunto de herramientas:

- Supervise su experiencia de usuario en Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server.

- Ver y solucionar problemas en toda la red.

- Asigne roles de soporte técnico y de administrador para Análisis de llamadas, de modo que pueda habilitar a los trabajadores del departamento de soporte técnico para que puedan ver y solucionar sus áreas de responsabilidad.

Con Call Data Connector, Skype Empresarial Server inserta los datos de llamadas en el servicio en la nube para que pueda aprovechar las herramientas análisis de llamadas (CA) y panel de calidad de llamadas (CQD) de Skype Empresarial Online, como se muestra en el siguiente diagrama:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

El servidor inserta los datos de calidad de experiencia (QoE) y registro detallado de llamadas (CDR) en el servicio en línea.

Las herramientas análisis de llamadas y CQD permiten supervisar la calidad de las llamadas y solucionar problemas de conexión con Microsoft Teams y los servicios de Skype Empresarial de la siguiente manera:

- Análisis de llamadas se centra en problemas de calidad con llamadas específicas. Muestra información detallada acerca de las llamadas y reuniones de cada usuario en una cuenta de Skype Empresarial.  Con Análisis de llamadas, puede asignar permisos a un operador del departamento de soporte técnico que pueda supervisar las llamadas sin tener acceso al resto del Centro de administración de Skype Empresarial.

- El Panel de calidad de llamadas se centra en el rendimiento de la red y los problemas en toda una organización. Los administradores de Skype Empresarial y los ingenieros de red usan esta herramienta para solucionar problemas y optimizar el rendimiento de la red.

Para obtener más información, consulte [Análisis de llamadas y Panel de calidad de llamadas.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Por supuesto, es posible que desee mantener algunos datos de calidad de llamadas localmente. Este puede ser el caso, por ejemplo, si usa una solución de terceros con informes y flujos de trabajo personalizados.  Call Data Connector le permite configurar el envío de datos al servicio en línea al mismo tiempo que guarda una copia de los datos en el servidor local, como se muestra en el siguiente diagrama:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server implementado en una topología compatible.  Para obtener más información acerca de la implementación de Skype Empresarial Server y [topologías admitidas, vea Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md). Para configurar Call Data Connector, debe:

- Habilitar la conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar Call Data Connector, debe asegurarse de que tiene la conectividad híbrida configurada entre los entornos locales y los entornos en línea. A veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 u Office 365](plan-hybrid-connectivity.md) y [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 u Office 365](configure-hybrid-connectivity.md).

- Autentique en su organización de Microsoft 365 u Office 365 y asegúrese de que tiene los siguientes roles habilitados:

  - Administrador de Skype Empresarial Server
  - Administrador global de Microsoft 365 u Office 365

- Si aún no lo ha hecho, active el Panel de calidad de llamadas como se describe en Activar y usar el Panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Habilite el grupo de servidores front-end para la supervisión, con bases de datos locales de LCSCdr y QoEMetrics. Sin esto, Call Data Connector no tendrá datos de métricas con los que trabajar.

> [!IMPORTANT]
> Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

- Autenticación de servidor a servidor configurada [correctamente.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparación de informes locales y en línea del Panel de calidad de llamadas (CQD)

| Informes de características | Skype Empresarial Online | Skype Empresarial Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de uso compartido de aplicaciones |Sí | Limitado |
| Información de creación de clientes| Sí | Sí |
| Análisis de obtención de detalles | Sí | No |
| Métricas de confiabilidad de medios | Sí | Limitado |
| Informes personalizados | Sí | Sí |
| Informes de información general | Sí | No |
| Informes por usuario | Sí | Sí |
| Personalización del conjunto de informes <br> (agregar, eliminar, modificar informes) | Sí | Sí |
| Métricas de uso compartido de pantalla basadas en vídeo | Sí | No |
| API de datos para acceso mediante programación <br> a CQD | No | Sí |
||||