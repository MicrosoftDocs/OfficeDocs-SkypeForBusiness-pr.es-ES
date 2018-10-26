---
title: "Configurar planes de marcado para las conferencias de acceso telefónico local"
TOCTitle: Configurar planes de marcado para las conferencias de acceso telefónico local
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48276261
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-25_

Para implementar la característica de conferencia de acceso telefónico local, necesita crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso. Asegúrese de que por lo menos una regla de normalización de cada plan de marcado convierta las extensiones telefónicas en números de teléfono completos en formato E.164. Los usuarios de la conferencia de acceso telefónico se unen a las conferencias como usuarios de empresa autenticados escribiendo su número de identificación personal (PIN) y su número de teléfono. Necesita una regla de normalización para convertir las extensiones en números de teléfono completos, de modo que los usuarios puedan autenticarse cuando introduzcan una extensión telefónica.

Para configurar planes de marcado para conferencias de acceso telefónico local, haga lo siguiente:

  - Tanto si implementa Telefonía IP empresarial como si no, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y para garantizar que una regla de normalización convierta de forma precisa los números de acceso telefónico. Para obtener instrucciones detalladas, vea [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si no implementó Telefonía IP empresarial, cree planes de marcado para los números de acceso de conferencia de acceso telefónico local. Recuerde incluir una región de conferencia de acceso telefónico local. Para obtener instrucciones detalladas, consulte [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si implementó Telefonía IP empresarial, modifique los planes de marcado de Telefonía IP empresarial según sea necesario para incluir regiones y usar las reglas de normalización pertinentes para los números de acceso telefónico. Para obtener instrucciones detalladas, consulte [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). También puede crear planes de marcado dedicados que solo se usarán para números de acceso telefónico. Para obtener instrucciones detalladas, consulte [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Para obtener información detallada sobre la planeación de regiones, consulte [Planeación de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación sobre planeación.

## En esta sección

  - [Ver la información del plan de marcado en Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

