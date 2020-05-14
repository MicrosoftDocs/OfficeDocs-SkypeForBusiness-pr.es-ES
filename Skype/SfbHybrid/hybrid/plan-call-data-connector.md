---
title: Conector de datos de llamada del plan | Panel de calidad de llamadas supervisión de análisis híbrido
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
description: Información general sobre el uso de las herramientas de telemetría de Skype empresarial online para supervisar una implementación local en un escenario híbrido.
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221320"
---
# <a name="plan-call-data-connector"></a>Conector de datos de llamada del plan

## <a name="overview"></a>Información general

En este tema se describen las ventajas, las consideraciones de planeación y los requisitos para implementar el conector de datos de llamada de Skype empresarial Server. Para obtener más información acerca de la configuración del conector de llamadas de datos, vea [Configure Call Data Connector](configure-call-data-connector.md).


Call Data Connector simplifica enormemente la supervisión de llamadas en un entorno híbrido porque ya no es necesario usar distintos conjuntos de herramientas locales y en línea para supervisar a todos los usuarios la calidad de las llamadas. Independientemente de si los usuarios están hospedados en local o en línea, puede elegir ver la calidad de las llamadas de toda la organización en línea.

Con el conector de datos de llamada, puede realizar las siguientes tareas mediante un único conjunto de herramientas:

- Supervise la experiencia del usuario en Microsoft Teams, en Skype empresarial online y en Skype empresarial Server.

- Ver y solucionar problemas en la red.

- Asignar roles de administrador y de asistencia técnica a los análisis de llamadas, de modo que pueda hacer que los trabajadores del Departamento de soporte vean y solucionen problemas de sus áreas de responsabilidad.

Con Call Data Connector, Skype empresarial Server inserta los datos de llamada en el servicio de nube para que pueda aprovechar las herramientas de análisis de llamadas en línea (CA) y del panel de calidad de llamadas (CQD) de Skype empresarial, tal como se muestra en el siguiente diagrama:

![Correo de voz de nube de SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

El servidor inserta los datos de calidad de la experiencia (QoE) y registro detallado de llamadas (CDR) en el servicio en línea.

El análisis de llamadas y las herramientas de CQD le permiten supervisar la calidad de las llamadas y solucionar los problemas de conexión con Microsoft Teams y los servicios de Skype empresarial de la siguiente manera:

- El análisis de llamadas se centra en problemas de calidad con llamadas específicas. Muestra información detallada sobre las llamadas y las reuniones de cada usuario en una cuenta de Skype empresarial.  Con el análisis de llamadas, puede asignar permisos a un operador del Departamento de soporte técnico que pueda supervisar las llamadas sin tener acceso al resto del centro de administración de Skype empresarial.

- El panel de calidad de llamadas se centra en el rendimiento y los problemas de la red en toda la organización. Los administradores de Skype empresarial y los ingenieros de red usan esta herramienta para solucionar problemas y optimizar el rendimiento de la red.

Para obtener más información, consulte [análisis de llamadas y panel de calidad de llamadas](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Por supuesto, es posible que desee mantener algunos datos sobre la calidad de las llamadas en las instalaciones locales. Esto puede ocurrir, por ejemplo, si usa una solución de terceros con flujos de trabajo y informes personalizados.  Call Data Connector permite configurar el envío de datos al servicio en línea, al mismo tiempo que se conserva una copia de los datos en el servidor local, tal y como se muestra en el siguiente diagrama:

![Correo de voz de nube de SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requirements

En los siguientes requisitos se da por supuesto que ya ha implementado Skype empresarial Server en una topología compatible.  Para obtener más información acerca de la implementación de Skype empresarial Server y las topologías admitidas, consulte [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Para configurar el conector de datos de llamada, debe:

- Habilitar la conectividad híbrida. Si ya ha implementado Skype empresarial Server y desea habilitar el conector de datos de llamada, debe asegurarse de que tiene establecida la conectividad híbrida entre su entorno local y el entorno en línea. A veces, se denomina configuración de dominio dividido.

   Para obtener más información, vea [plan Hybrid Connectivity between Skype for Business Server y microsoft 365 u office 365](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida entre Skype empresarial server y Microsoft 365 u Office 365](configure-hybrid-connectivity.md).

- Autentique en su organización de Microsoft 365 u Office 365 y asegúrese de que tiene las siguientes funciones habilitadas:

  - Administrador de Skype empresarial Server
  - Administrador global de Microsoft 365 o Office 365

- Si aún no lo ha hecho, active el panel de calidad de llamadas como se describe en [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Habilitar el grupo de servidores front-end para la supervisión con bases de datos locales de LCSCdr y QoEMetrics. Sin esto, Call Data Connector no tendrá datos de métricas con los que trabajar.

> [!IMPORTANT]
> Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

- [La autenticación de servidor a servidor se](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)ha configurado correctamente. 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparación de informes de panel de calidad de llamadas locales y en línea (CQD)

| Informes de características | Skype Empresarial Online | Skype Empresarial Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Métrica de uso compartido de aplicaciones |Sí | Limitada |
| Información del edificio del cliente| Sí | Sí |
| Análisis de desglose | Yes | No |
| Métricas de confiabilidad de medios | Sí | Limitada |
| Informes precodificados | Sí | Sí |
| Informes de información general | Yes | No |
| Informes por usuario | Sí | Sí |
| Personalización del conjunto de informes <br> (agregar, eliminar, modificar informes) | Sí | Sí |
| Métricas de uso compartido de pantalla basado en vídeo | Yes | No |
| API de datos para el acceso mediante programación <br> a CQD | No | Sí |
||||
