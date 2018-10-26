---
title: Componentes que se usan en la respuesta de llamadas en grupo
TOCTitle: Componentes que se usan en la respuesta de llamadas en grupo
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945625(v=OCS.15)
ms:contentKeyID: 52061672
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes que se usan en la respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2013-01-30_

La atención de llamadas grupales se implementa automáticamente al implementar Telefonía IP empresarial y el Aplicación de estacionamiento de llamadas. Para habilitar la atención de llamadas grupales, debe configurar la tabla de órbitas de Estacionamiento de llamadas con intervalos de números independientes designados como números de grupo de atención de llamadas y, luego, asignar los usuarios a grupos de atención de llamadas y habilitarlos para la atención de llamadas grupales. Los siguientes componentes de Lync Server admiten la atención de llamadas grupales:

  - **Servicio de aplicaciones**   El Servicio de aplicaciones proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como el Aplicación de estacionamiento de llamadas. El Servicio de aplicaciones se instala automáticamente en cada servidor front-end de un Grupo de servidores front-end y en cada servidor Standard Edition.

  - **Aplicación de estacionamiento de llamadas**   El Aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas hospedadas por el Servicio de aplicaciones. La atención de llamadas grupales se basa en el Aplicación de estacionamiento de llamadas.

  - **Shell de administración de Lync Server**   Para administrar los grupos de atención de llamadas grupales, debe usar el Shell de administración de Lync Server.

  - **Herramientas del kit de recursos de SEFAUtil**   Para asignar los usuarios a un grupo de atención de llamadas y para habilitar o deshabilitar la atención de llamadas para estos usuarios, debe usar la utilidad de activación de características de extensión secundaria (SEFAUtil).

